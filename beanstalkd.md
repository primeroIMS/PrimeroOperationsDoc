# Beanstalkd

Beanstalk \([https://github.com/kr/beanstalkd/wiki/faq](https://github.com/kr/beanstalkd/wiki/faq)\) is a queue for processes. Currently, beanstalk is by Primero for bulk exports. Beanstalk prevents the system from getting overwhelmed by thousands of tasks and just queues up the tasks until the system has enough resources.

| Start | `$ sudo systemctl start beanstalkd` |
| :--- | :--- |
| Stop | `$ sudo systemctl stop beanstalkd` |
| Status | `$ sudo systemctl status beanstalkd`<br>*beanstalkd.service - Simple, fast work queue*<br>*Loaded: loaded (/lib/systemd/system/beanstalkd.service; enabled; vendor preset: enabled)*<br>*Active: active (running) since Tue 2017-09-19 04:17:53 UTC; 11h ago*<br>*Docs: man:beanstalkd(1)*<br>*Main PID: 1086 (beanstalkd)*<br>*Tasks: 1*<br>*Memory: 1.0M*<br>*CPU: 5ms*<br>*CGroup: /system.slice/beanstalkd.service*<br>*&emsp;&emsp;&emsp;└─1086 /usr/bin/beanstalkd -l localhost -p 11300 -b /srv/primero/beanstalkd*<br>*Sep 19 04:17:53 primero-int-1-4 systemd[1]: Started Simple, fast work queue.*<br><br>`$ ps -fA \| grep beanstalkd`<br>*beansta+  1086     1  0 04:17 ?        00:00:00 /usr/bin/beanstalkd -l localhost -p 11300 -b /srv/primero/beanstalkd* |
| Log Files | /srv/primero/logs/solr/output.log |
| Run User | root, primero |



