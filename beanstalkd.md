# Beanstalkd

Beanstalk \([https://github.com/kr/beanstalkd/wiki/faq](https://github.com/kr/beanstalkd/wiki/faq)\) is a queue for processes. Currently, beanstalk is by Primero for bulk exports. Beanstalk prevents the system from getting overwhelmed by thousands of tasks and just queues up the tasks until the system has enough resources.

| Start | `$ sudo /etc/init.d/beanstalkd` start |
| :--- | :--- |
| Stop | `$ sudo /etc/init.d/beanstalkd stop` |
| Status | `$ echo -e "stats\r\n" \| nc localhost 11300`<br>*OK 898*<br>*---*<br>*current-jobs-urgent: 0*<br>*current-jobs-ready: 0*<br>*current-jobs-reserved: 0*<br>*...*<br>*binlog-records-written: 0*<br>*binlog-max-size: 10485760*<br>*id: a1ba6cd827c9b4c1*<br>*hostname: vagrant*<br><br>`$ ps -fA \| grep beanstalkd`<br>*beansta+ 2306 1 0 17:30 ? 00:00:00 /usr/bin/beanstalkd -l localhost -p 11300 -b /srv/primero/beanstalkd* |
| Log Files | /srv/primero/logs/solr/output.log |
| Run User | root, primero |



