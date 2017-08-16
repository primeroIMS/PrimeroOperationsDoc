# CouchDB

CouchDB \([http://couchdb.apache.org](http://couchdb.apache.org/)\) is the backing database of Primero. It is accessible via HTTP on 127.0.0.1:5984 and is optionally reverse proxied by Nginx for HTTPS on 0.0.0.0:6984. This exposes CouchDB to the outside world for replication.

The admin is exposed at [https://cpims-myimplementation.primero.org:6984/\_utils](https://cpims-myimplementation.primero.org:6984/_utils).

If CouchDB is not exposed to the external world, one will need to set up a SSH tunnel and forward the port to the localhost in order to access it for maintenance:

`$ ssh -f -N -L 45984:localhost:5984 admin_user@your_primero_server`

The admin will now be available at [http://localhost:45984/\_utils](http://localhost:45984/_utils)

CouchDB is started as a service on system startup via the Upstart Daemon \([http://upstart.ubuntu.com/](http://upstart.ubuntu.com/)\)

| Start | `$ sudo start couchdb` |
| :--- | :--- |
| Stop | `$ sudo stop couchdb` |
| Status | `$ sudo initctl list \| grep couchdb`<br>*couchdb start/running, process 6332*<br><br>`$ ps -fA \| grep couchdb`<br>*root 6332 1 0 21:20 ? 00:00:00 su couchdb -c /usr/bin/couchdb*<br>*couchdb 6334 6332 1 21:20 ? 00:00:16 /usr/lib/erlang/erts-5.10.4/bin/beam.smp -Bd -K true -A 4 -- -root /usr/lib/erlang -progname erl -- -home /var/lib/couchdb -- -noshell -noinput -os\_mon start\_memsup false start\_cpu\_sup false disk\_space\_check\_interval 1 disk\_almost\_full\_threshold 1 -sasl errlog\_type error -couch\_ini /etc/couchdb/default.ini /etc/couchdb/local.ini -s couch*<br>*couchdb 6354 6334 0 21:20 ? 00:00:00 sh -s disksup* |
| Log File | /srv/primero/logs/couchdb/couch.log |
| Data Dir | /var/lib/couchdb |
| User | root, couchdb |

# 



