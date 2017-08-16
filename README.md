# Primero Application

![](/img/media/primero.jpg)Primero is a Ruby on Rails application. It is served by Phusion Passenger which is proxied to by an Nginx web server. Static assets such as JS, CSS, and application icons and images are served by Nginx.

Nginx is configured to serve Primero via HTTPS. It runs on default port HTTPS 443 which accepts traffic redirected from port 80.

The backing database is CouchDB. When CouchDB is configured to replicate, it will be running on port 6984, via HTTPS.

The core run-time system dependencies of Primero are:

* Nginx, which accepts external web traffic and routes it to Phusion Passenger or serves up static assets

* Phusion Passenger which launches and services 1-N Ruby processes

* CouchDB, the database backing Primero \(see below\)

* Apache Solr, the Lucene search index service \(see below\)

The following services ensure proper Primero behavior when applying business rules, but will not cause fatal application errors if they are down:

* Couch Change Watcher notifier

* Primero Scheduler

The system is designed to be deployed to Ubuntu 16.04, the long term support edition which is guaranteed to be supported through the end of 2020. All deployment is automated using Chef \([https://www.chef.io/](#)\).

