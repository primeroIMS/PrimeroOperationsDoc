# Backburner

Backburner \([https://github.com/nesquena/backburner/wiki](https://github.com/nesquena/backburner/wiki)\) is ‘queue consumer’ which takes items from the beanstalk queue and executes them as resources become available.

| Start | `$ sudo supervisorctl start backburner` |
| :--- | :--- |
| Stop | `$ sudo supervisorctl stop backburner` |
| Status | `$ sudo supervisorctl status backburner`<br>*backburner                       RUNNING   pid 7915, uptime 11:04:12*<br><br>`$ ps -fA \| grep backburner`<br>*primero   7915  1423  0 05:02 ?        00:00:00 /bin/bash /srv/primero/application/daemons/backburner-worker.sh*<br>*primero   8005  7915  0 05:02 ?        00:00:02 ruby /srv/primero/.rvm/gems/ruby-2.1.5-railsexpress/bin/rake backburner:work*<br>*primero   8566  8005  0 05:02 ?        00:00:00 ruby /srv/primero/.rvm/gems/ruby-2.1.5-railsexpress/bin/rake backburner:work* |
| Log Files | /srv/primero/logs/solr/output.log |
| Run User | root, primero |



