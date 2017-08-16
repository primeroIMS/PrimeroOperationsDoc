# Primero Scheduler

The Primero scheduler runs periodic data maintenance tasks. It corrects or updates data:

* Updates age based on birthday

* Auto generates flags to prompt for follow ups \(functionality not used in SL\)

In the future other maintenance tasks will be added

The Primero scheduler is based on the Rufus Scheduler gem \([https://github.com/jmettraux/rufus-scheduler](https://github.com/jmettraux/rufus-scheduler)\). It is launched as a process using Rake tasks as an application process.

Note the RAILS\_SCHEDULER\_LOGDIR is /srv/primero/logs/scheduler on a default system.

For Sierra Leone AWS deploy, RAILS\_SCHEDULER\_LOGDIR is /data/logs/scheduler

| Start | `$ sudo supervisorctl start primero-scheduler` |
| :--- | :--- |
| Stop | `$ sudo supervisorctl start primero-scheduler` |
| Status | `$ sudo supervisorctl status`<br>*backburner RUNNING pid 10570, uptime 5:28:23*<br>*couch-watcher RUNNING pid 10580, uptime 5:28:23*<br>*primero-scheduler RUNNING pid 10587, uptime 5:28:23*<br>*solr RUNNING pid 10307, uptime 5:28:23*<br>*who-watches-the couch watcher RUNNING pid 10555, uptime 5:28:23*<br><br>`$ ps -fA \| grep primero-scheduler`<br>*primero 22121 1 0 Jul23 ? 00:00:25 primero-scheduler* |
| Log Files | /srv/primero/logs/scheduler/primero-scheduler.output |
| Run User | root, primero |



