# Mission Reflection

The shift from `docker run` to Docker Compose is really a shift from describing
actions to describing a desired state. When I typed commands by hand, every
deployment was a small performance: I had to remember the port mapping, the
environment variables, the order things started in, and if I got one flag wrong
the container came up subtly broken and I had to figure out which of a dozen
arguments was at fault. None of that knowledge lived anywhere except in my head
and my shell history.

A `docker-compose.yml` file moves all of it into a version-controlled artifact.
The deployment becomes something I can read, review, and hand to someone else.
If a teammate clones the repository, they get the same stack by running one
command, not by reconstructing my terminal session from memory. If something
breaks six months from now, the file itself shows what was supposed to be
running. That is the real value of Infrastructure as Code — not that it saves
typing, but that it turns a deployment into a document that can be examined and
reused instead of a sequence of steps that has to be remembered. Manual commands
drift; people adapt them on the fly and forget to write down what they changed.
A Compose file is the single source of truth, so the environment I test in and
the one I hand over are guaranteed to match.

YAML is unusual in that whitespace is not cosmetic — indentation is the syntax.
Where a language like Python uses braces or a language like JSON uses brackets,
YAML uses indentation depth to express which keys belong to which parent. That
makes an indentation error a structural error, not a formatting one. There are
two failure modes, and the second is worse than the first. The benign case is
that the parser rejects the file outright and tells you the line number; you fix
the tab, save, and rerun. The dangerous case is that the file parses
successfully but the structure is wrong — a key ends up nested one level too
deep, so it becomes a property of the wrong object rather than a sibling. In
that situation Compose runs happily and produces a configuration different from
the one you intended, and you have to debug the running containers to discover a
mistake that was sitting in the file the whole time. This is why the lab
emphasized spaces and warned against tabs specifically: a tab character is
invisible at a glance but semantically distinct from the spaces around it, so
the error is nearly impossible to spot by eye.

Environment variables exist to separate configuration from the image. The
MariaDB image is identical everywhere it runs; what differs between environments
is the data it receives — database name, user, password. Passing those values as
environment variables means one image can serve development, staging, and
production without being rebuilt. There is also a coordination problem the
variables solve directly. Two containers have to agree on the same database
name, the same user, and the same password, or the connection fails; writing
those values into both blocks as literal strings would work, but it creates two
facts that can drift apart when someone edits one and forgets the other.
Declaring them in the same file keeps them visibly paired. `MYSQL_HOST=database`
is the same principle applied to a different problem — the app container has no
idea what IP the database container will receive, and that address changes when
the stack restarts, so rather than hard-coding it the app learns the target from
its environment and relies on Compose's DNS to resolve the service name. One
honest weakness belongs here: in this proof-of-concept the passwords are written
in plain text in the file. In a real deployment those values would come from a
secret manager or an untracked `.env` file, because committing credentials to
version control defeats much of the point.

It felt surprisingly ordinary, which was the interesting part. I ran the deploy
command and waited — the bulk of the time was image download, not configuration
— and then a working Nextcloud setup screen appeared at the port I had
forwarded. There was no moment of wiring anything together. That ordinariness
was the lesson. Installing Nextcloud manually would mean a web server, PHP with
the correct extensions, a database, and the connection between them, all
configured by hand and all capable of failing in their own ways. The Compose
file had already described all of that, and the containers assembled it on their
own; what looked like a full server build was really two declarations and a
network. The anticlimax was also a little uncomfortable, because it is easy to
feel like nothing was learned when the hard part is compressed into a file I
copied. The work was in understanding why the file was shaped the way it was,
which is the part that does not happen automatically.

At the start I understood cloud computing mostly as a business arrangement:
instead of buying servers, you rent someone else's. That is accurate but it is
only the surface. Working through these missions showed me that the cloud is a
set of layers stacked on that premise, and each layer exists to remove a
different kind of manual work — physical hardware, then virtual machines, then
containers, then the orchestration that ties containers together. The most
useful change is how I now think about a deployment itself. Early on I thought
of it as a sequence of things you do: install this, configure that, start the
other. Now I think of it as an artifact — the Compose file is a description of a
system, and the commands just apply that description. That reframing is what
separates the two kinds of engineer the lab described, the one who types
commands and the one who writes code that produces the system. The progression
across the missions mirrors that shift deliberately: I started by learning what
the infrastructure is, then how to describe it, and now how to write it in a
form a machine can execute and a person can review. I still have a lot to learn
about how this scales past a laptop, but the shape of the discipline is clearer
now than it was in Mission 1.
