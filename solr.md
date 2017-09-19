# Solr

Apache Solr \([http://lucene.apache.org/solr/](http://lucene.apache.org/solr/)\) is used as the search and query index for Primero. All records saved in Primero are indexed in Solr. Solr is a Java process that runs on a Jetty application server.

Solr is launched by Supervisor \([http://supervisord.org/](http://supervisord.org/)\). A nightly cron job restarts Solr to prevent the memory cache from over-expanding.

| Start | `$ sudo supervisorctl start solr` |
| :--- | :--- |
| Stop | `$ sudo supervisorctl stop solr` |
| Status | `$ sudo supervisorctl status solr`<br>*solr                             RUNNING   pid 14899, uptime 9:52:10*<br><br>`$ ps -fA \| grep solr`<br>*solr     14899  1423  0 06:25 ?        00:00:32 java -Djetty.port=8983 -Dsolr.data.dir=/srv/primero/application/solr/data/production -Dsolr.solr.home=/srv/primero/application/solr -Djava.awt.headless=true -jar start.jar* |
| Reindex | `$ RAILS_ENV=production bundle exec rake sunspot:reindex` |
| Log Files | /srv/primero/logs/solr/output.log |
| Run User | root, solr |

# 



