# Nginx

The Primero application is served by the Nginx server. Shutting the server down halts the application.

Note that **Nginx** is an optional runtime dependency of CouchDB for situations where external syncing is employed \(as it is in Sierra Leone\). Where CouchDB and the Primero Ruby on Rails application are deployed on the same box, they will share an instance of Nginx.

| Start | `$ sudo systemctl start nginx` |
| :--- | :--- |
| Stop | `$ sudo systemctl stop nginx` |
| Status | `$ sudo systemctl status nginx`<br>*nginx.service - A high performance web server and a reverse proxy server*<br>*Loaded: loaded (/lib/systemd/system/nginx.service; enabled; vendor preset: enabled)*<br>*Active: active (running) since Tue 2017-09-19 05:02:53 UTC; 10h ago*<br>*Process: 12520 ExecStart=/usr/sbin/nginx -g daemon on; master_process on; (code=exited, status=0/SUCCESS)*<br>*Process: 12517 ExecStartPre=/usr/sbin/nginx -t -q -g daemon on; master_process on; (code=exited, status=0/SUCCESS)*<br>*Main PID: 12523 (nginx)*<br>*Tasks: 3*<br>*Memory: 8.0M*<br>*CPU: 2.987s*<br>*CGroup: /system.slice/nginx.service*<br>*&emsp;&emsp;&emsp;├─12523 nginx: master process /usr/sbin/nginx -g daemon on; master_process on*<br>*&emsp;&emsp;&emsp;├─12524 nginx: worker process*<br>*&emsp;&emsp;&emsp;└─12525 nginx: worker process*<br>*Sep 19 05:02:53 primero-int-1-4 systemd[1]: Starting A high performance web server and a reverse proxy server...*<br>*Sep 19 05:02:53 primero-int-1-4 nginx[12517]: nginx: [warn] "ssl_stapling" ignored, issuer certificate not found*<br>*Sep 19 05:02:53 primero-int-1-4 nginx[12520]: nginx: [warn] "ssl_stapling" ignored, issuer certificate not found* <br><br> `$ ps -fA \| grep nginx`<br>*root     12523     1  0 05:02 ?        00:00:00 nginx: master process /usr/sbin/nginx -g daemon on; master_process on;*<br>*www-data 12524 12523  0 05:02 ?        00:00:02 nginx: worker process*<br>*www-data 12525 12523  0 05:02 ?        00:00:00 nginx: worker process*|
|
| Log Files | /srv/primero/logs/couchdb/nginx\_server.log<br>/srv/primero/logs/couchdb/nginx\_error.log<br>/var/log/nginx/access.log |
| Run User | root, www-data |



