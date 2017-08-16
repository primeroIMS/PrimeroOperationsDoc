# Backburner

Backburner \([https://github.com/nesquena/backburner/wiki](https://github.com/nesquena/backburner/wiki)\) is ‘queue consumer’ which takes items from the beanstalk queue and executes them as resources become available.

| Start | $ sudo service backburner start |
| :--- | :--- |
| Stop | $ sudo service backburner stop |
| Status | `$ sudo supervisorctl status`<br>*backburner RUNNING pid 10570, uptime 5:28:23*<br>*couch-watcher RUNNING pid 10580, uptime 5:28:23*<br>*primero-scheduler RUNNING pid 10587, uptime 5:28:23*<br>*solr RUNNING pid 10307, uptime 5:28:23<br>who-watches-the couch watcher RUNNING pid 10555, uptime 5:28:23*<br><br>`$ ps -fA \| grep backburner`primero 2635 2510 0 17:30 ? 00:00:00 /bin/bash /srv/primero/application/daemons/backburner-worker.shprimero 3167 2635 0 17:30 ? 00:00:06 ruby /srv/primero/.rvm/gems/ruby-2.1.5-railsexpress/bin/rake backburner:workprimero 3966 3167 0 17:30 ? 00:00:00 ruby /srv/primero/.rvm/gems/ruby-2.1.5-railsexpress/bin/rake backburner:work |
| Log Files | /srv/primero/logs/solr/output.log |
| Run User | root, primero |



