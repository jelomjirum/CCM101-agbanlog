
# Laboratory 08 - Mission Reflection

## Cloud Security Engineer

During Laboratory 08, I gained a better understanding of how firewall configuration helps protect cloud servers from possible security threats. This activity showed me that maintaining a secure server is just as important as making sure applications are running properly.

One important lesson I learned is how a host-based firewall provides protection even when the main network security has been bypassed. Since the firewall operates directly on the server, it can still inspect and control incoming connections based on established rules. This additional protection helps prevent unauthorized users from accessing services that should remain restricted.

I also discovered why controlling open ports is an essential responsibility of a system administrator. Each open port may provide access to a running service, which could become a target for attackers. Keeping unnecessary ports closed helps minimize security risks. In our laboratory, we focused on allowing only the connections needed for SSH and the Nginx web application. This taught me that proper port management is an effective way to reduce possible entry points into a system.

Another lesson involves the risks of exposing database services to the internet. For example, if MySQL port 3306 is publicly accessible, attackers may attempt to guess passwords, exploit software weaknesses, or gain unauthorized access to sensitive information. To prevent these problems, database connections should only be available to trusted systems and authorized users.

Through this activity, I became more familiar with UFW commands and the importance of reviewing firewall settings. I also realized that server security requires regular maintenance and careful decision-making.

Overall, Laboratory 08 improved my understanding of cloud security and helped me develop practical skills in managing network access. These lessons will be useful when configuring and maintaining servers in future projects.

