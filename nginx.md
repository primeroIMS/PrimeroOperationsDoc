# Nginx

The Primero application is served by the Nginx server. Shutting the server down halts the application. If there is instability or unpredictable behavior experienced after applying a configuration bundle, stopping then starting Nginx is a good approach to resolving them.

Note that **Nginx** is an optional runtime dependency of CouchDB for situations where external syncing is employed \(as it is in Sierra Leone\). Where CouchDB and the Primero Ruby on Rails application are deployed on the same box, they will share an instance of Nginx.

| Start | `$ sudo service nginx start` |
| :--- | :--- |
| Stop | `$ sudo service nginx stop` |
| Status | `$ sudo service nginx status`<br>*nginx.service - A high performance web server and a reverse proxy server*<br>*Loaded: loaded \(/lib/systemd/system/nginx.service; enabled; vendor preset: en*<br>*Active: active \(running\) since Tue 2017-08-15 18:11:50 UTC; 41min ago*<br>*Process: 6358 ExecStop=/sbin/start-stop-daemon --quiet --stop --retry QUIT/5 -*<br>*Process: 6416 ExecStart=/usr/sbin/nginx -g daemon on; master\_process on; \(codeProcess: 6412 ExecStartPre=/usr/sbin/nginx -t -q -g daemon on; master\_process*<br>*Main PID: 6419 \(nginx\)*<br>*    Tasks: 3*<br>*  Memory: 4.4M*<br>*    CPU: 343ms*<br>*  CGroup: /system.slice/nginx.service*<br>*    \|-6419 nginx: master process /usr/sbin/nginx -g daemon on; master\_pro*<br>*    \|-6420 nginx: worker process*<br>*    \`-6421 nginx: worker process*<br><br>`$ ps -fA \| grep nginx`<br>*root 10701 1 0 14:05 ? 00:00:00 nginx: master process /usr/sbin/nginx*<br>*www-data 10702 10701 0 14:05 ? 00:00:04 nginx: worker process*<br>*www-data 10703 10701 0 14:05 ? 00:00:04 nginx: worker process*<br>*www-data 10704 10701 0 14:05 ? 00:00:00 nginx: worker process*<br>*www-data 10705 10701 0 14:05 ? 00:00:04 nginx: worker process* |
| Log Files | /srv/primero/logs/couchdb/nginx\_server.log<br>/srv/primero/logs/couchdb/nginx\_error.log/var/log/nginx/access.log |
| Run User | root, www-data |



