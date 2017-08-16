# Security

It is assumed that Primero will be running on Linux Ubuntu 16.04. This is an LTS release which will be maintained for system-level security until the end of the year 2020.

The Primero Chef deployment automation deploys the application stack in a consistent way, system to system. Application deployment level security fixes are regularly applied to the Chef scripts.

Rudimentary system deployment security best practices include:

* Maintaining the latest security packages. As of v1.1.6, Primero can optionally be deployed along with the **unattended-upgrades** Ubuntu package. This will run nightly and check for and apply the latest security updates. See [https://help.ubuntu.com/lts/serverguide/automatic-updates.html](https://help.ubuntu.com/lts/serverguide/automatic-updates.html). This is configured via the Chef deployment.

* Configuring and locking down SSH access. It is assumed that SSH passwordless access is implemented.

* Configuring firewall rules. Do not expose ports unless they are necessary for the application and its support

  * 80, 443 for HTTP/HTTPS. The server will automatically redirect 80 to 443. Unencrypted HTTP traffic is not supported.

  * 22 for SSH access. This can be further restricted by locking down a range of machines that are allowed to access it.

  * 6984 for CouchDB replication. This is necessary only where local instances are syncing with a central server and should be locked down in a deployment where no local instances exist.

* Primero assumes HTTPS. SSL certificates will need to be obtained either through a local CA or purchased from an SSL vendor. As of Primero v1.1.6, domain-verified, free, and self-updating Let’s Encrypt SSL certificates can be used. See [https://letsencrypt.org/](https://letsencrypt.org/). This is configured via the Chef deployment.

A good starting point for locking down an Ubuntu Linux environment can be found in this guide: [https://www.linode.com/docs/security/securing-your-server\#debian--ubuntu](https://www.linode.com/docs/security/securing-your-server#debian--ubuntu).

