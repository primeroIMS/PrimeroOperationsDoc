# primeroctl Script

The primeroctl script should be used to act simulaneously on all of the primero applications. so you can simultaneously start, stop or check the status of: CouchDB, Nginx, Passenger, Solr, Beanstalkd, Backburner, CouchWatcher, and Primero Scheduler.

| Start | `$ sudo /srv/primero/bin/primeroctl start` |
| :--- | :--- |
| Stop | `$ sudo /srv/primero/bin/primeroctl stop` |
| Status | `$ sudo /srv/primero/bin/primeroctl status`<br>*Primero status:*<br>*nginx:&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;active (running) since Tue 2017-09-19 05:02:53 UTC; 12h ago*<br>*passenger:&emsp;&emsp;&emsp;&emsp;active (running) since Tue 2017-09-19 05:02:49 UTC; 12h ago*<br>*couch-watcher&emsp;&emsp;RUNNING   pid 11497, uptime 12:38:48*<br>*who-watches-the-couch-watcher&emsp;&emsp;&emsp;RUNNING   pid 11604, uptime 12:38:47*<br>*primero-scheduler&emsp;RUNNING   pid 10823, uptime 12:38:55*<br>*backburner&emsp;&emsp;&emsp;&emsp;RUNNING   pid 7915, uptime 12:39:24*<br>*beanstalkd:&emsp;&emsp;&emsp;&emsp;active (running) since Tue 2017-09-19 04:17:53 UTC; 13h ago*<br>*solr&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;RUNNING   pid 14899, uptime 11:16:06*<br>*couchdb:&emsp;&emsp;&emsp;&emsp;&emsp;active (running) since Tue 2017-09-19 05:01:44 UTC; 12h ago*|
| Run User | root |

