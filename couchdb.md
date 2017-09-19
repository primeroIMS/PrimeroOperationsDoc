# CouchDB

CouchDB \([http://couchdb.apache.org](http://couchdb.apache.org/)\) is the backing database of Primero. It is accessible via HTTP on 127.0.0.1:5984 and is optionally reverse proxied by Nginx for HTTPS on 0.0.0.0:6984. This exposes CouchDB to the outside world for replication.

The admin is exposed at [https://cpims-myimplementation.primero.org:6984/\_utils](https://cpims-myimplementation.primero.org:6984/_utils).

If CouchDB is not exposed to the external world, one will need to set up a SSH tunnel and forward the port to the localhost in order to access it for maintenance:

`$ ssh -f -N -L 45984:localhost:5984 admin_user@your_primero_server`

The admin will now be available at [http://localhost:45984/\_utils](http://localhost:45984/_utils)

CouchDB is started as a service on system startup via the Upstart Daemon \([http://upstart.ubuntu.com/](http://upstart.ubuntu.com/)\)

| Start | `$ systemctl start couchdb` |
| :--- | :--- |
| Stop | `$ systemctl stop couchdb` |
| Status | `$ systemctl status couchdb`<br>*couchdb.service - System-wide CouchDB instance*<br>*Loaded: loaded (/lib/systemd/system/couchdb.service; enabled; vendor preset: enabled)*<br>*Active: active (running) since Tue 2017-09-19 05:01:44 UTC; 10h ago*<br>*Main PID: 4515 (beam.smp)*<br>*Tasks: 14*<br>*Memory: 77.9M*<br>*CPU: 3min 44.982s*<br>*CGroup: /system.slice/couchdb.service*<br>*&emsp;&emsp;&emsp;├─ 4515 /usr/lib/erlang/erts-7.3/bin/beam.smp -Bd -K true -A 4 -- -root /usr/lib/erlang -progname erl -- -home /var/lib/couchdb -- -noshell -noinput -os_mon start_memsup false start_cpu_sup fal*<br>*&emsp;&emsp;&emsp;├─ 4553 sh -s disksup*<br>*&emsp;&emsp;&emsp;└─26184 /usr/bin/couchjs -S 134217728 /usr/share/couchdb/server/main.js*<br>*Sep 19 15:09:31 primero-int-1-4 couchdb[4515]: [info] [<0.5509.1>] 127.0.0.1 - - PUT /primero_system_settings_production/52ffbe061b4b930ce941ff9a8f9b526c 201*<br>*Sep 19 15:09:31 primero-int-1-4 couchdb[4515]: [info] [<0.5510.1>] 127.0.0.1 - - GET /primero_sessions_production/e3255dc9a0964d1292f75e51113e0f87 200*<br>*Sep 19 15:09:31 primero-int-1-4 couchdb[4515]: [info] [<0.32009.0>] Starting index update for db: primero_system_settings_production idx: _design/SystemSettings* |
| Log File | /srv/primero/logs/couchdb/couch.log |
| Data Dir | /var/lib/couchdb |
| Run Users | root, couchdb |

# 



