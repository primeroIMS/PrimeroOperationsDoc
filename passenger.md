# Passenger

Passenger is an open source, scalable web application server. If there is instability or unpredictable behavior experienced after applying a configuration bundle, stopping then starting Passenger is a good approach to resolving them.

| Start | `$ sudo systemctl start passenger` |
| :--- | :--- |
| Stop | `$ sudo systemctl stop passenger` |
| Status | `$ sudo systemctl status passenger`<br>*passenger.service - A high performance web server and a reverse proxy server*<br>*Loaded: loaded \(/lib/systemd/system/passenger.service; enabled; vendor preset: en*<br>*Active: active \(running\) since Tue 2017-08-15 18:11:50 UTC; 41min ago*<br>*Process: 6358 ExecStop=/sbin/start-stop-daemon --quiet --stop --retry QUIT/5 -*<br>*Process: 22702 ExecStart=/srv/primero/application/daemons/passenger-worker.sh start \(code=exited, status=0/SUCCESS\)*<br>*Tasks: 23*<br>*Memory: 152.3M*<br>*CPU: 9.54a*<br>*CGroup: /system.slice/passenger.service*<br>*\|-22841 PassengerWatchdog*<br>*\|-22844 PassengerHelperAgent*<br>*\|-22849 PassengerLoggingAgent*<br>*\|-22859 PassengerWebHelper: master process /srv/primero/.passenger/standalone/4.0.59/webhelper-1.6.2-x86_64-linux/PassengerWebHelper -c /tmp/passenger-standalone.1qxxnra/config -p /tmp/passenge*<br>*\|-22860 PassengerWebHelper: worker process*<br>*\|-22865 /srv/primero/.passenger/standalone/4.0.59/support-x86_64-linux/agents/TempDirToucher /tmp/passenger-standalone.1qxxnra --cleanup --daemonize --pid-file /tmp/passenger-standalone.1qxxnra*<br>*\`-22894 Passenger RackApp: /srv/primero/application*<br><br>`$ ps -fA \| grep passenger`<br>*primero  22859     1  0 21:01 ?        00:00:00 PassengerWebHelper: master process /srv/primero/.passenger/standalone/4.0.59/webhelper-1.6.2-x86_64-linux/PassengerWebHelper -c /tmp/passenger-standalone.1qxxnra/config -p /tmp/passenger-standalone.1qxxnra/*<br>*primero  22865     1  0 21:01 ?        00:00:00 /srv/primero/.passenger/standalone/4.0.59/support-x86_64-linux/agents/TempDirToucher /tmp/passenger-standalone.1qxxnra --cleanup --daemonize --pid-file /tmp/passenger-standalone.1qxxnra/temp\_dir\_toucher.pid --log-file /srv/primero/logs/rails//passenger.log*|
| Log File | /srv/primero/logs/rails/passenger.log |
| Run User | root, primero |



