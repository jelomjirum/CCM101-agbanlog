# Docker Compose Guide

## What the `services:` Block Does
Declares each container in the stack. Every key under it (`database`, `app`) is
one service; nested settings describe its image, environment, and ports.


## How the App Finds the Database
Compose places all services on one user-defined network and registers each
service name as a DNS name. `MYSQL_HOST=database` tells Nextcloud to resolve the
hostname `database`, which resolves to the MariaDB container's IP.


## `docker run` vs `docker-compose up -d`
`docker run` is imperative — one container, every flag retyped each time, config
lives in shell history. `docker-compose up -d` is declarative — the whole stack
is declared in a version-controlled file and created with
