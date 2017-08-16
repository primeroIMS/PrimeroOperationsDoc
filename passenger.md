# Passenger

If there is instability or unpredictable behavior experienced after applying a configuration bundle, stopping then starting Passenger is a good approach to resolving them.

| Start | `$ sudo systemctl start passenger` |
| :--- | :--- |
| Stop | `$ sudo systemctl stop passenger` |
| Status | `$ sudo systemctl status passenger` |
| Log File | /srv/primero/logs/rails/passenger.log |
| Run User | root, primero |



