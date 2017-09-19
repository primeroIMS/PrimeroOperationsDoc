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
| Status | `$ sudo supervisorctl status primero-scheduler`<br>*primero-scheduler                RUNNING   pid 10823, uptime 11:13:15*<br><br>`$ ps -fA \| grep primero-scheduler`<br>*primero  10823  1423  0 05:02 ?        00:00:00 /bin/bash /srv/primero/application/primero-scheduler-worker.sh* |
| Log Files | /srv/primero/logs/scheduler/primero-scheduler.output |
| Run User | root, primero |



