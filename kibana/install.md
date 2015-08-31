

```shell
 wget https://download.elastic.co/kibana/kibana/kibana-4.1.1-linux-x64.tar.gz
 tar xvf kibana-*.tar.gz
 sudo mkdir /opt/kibana
 sudo cp -R ~/kibana-4*/* /opt/kibana/
 cd /etc/init.d && sudo wget https://gist.githubusercontent.com/thisismitch/8b15ac909aed214ad04a/raw/bce61d85643c2dcdfbc2728c55a41dab444dca20/kibana4
 sudo chmod +x /etc/init.d/kibana4
 sudo update-rc.d kibana4 defaults 96 9
 sudo service kibana4 start
```

the kibana 4 start up script is in this repo as well if it is changed or missing from the above git account

update kibana.yml to set host: `"localhost"`
Kibana app server will only host locally, will set up nginx to proxy external traffic
also update kibana.yml, set `elasticsearch_url` to your elasticsearch server/cluster

nginx setup for kibana
```shell
 sudo apt-get install nginx apache2-utils
 sudo htpasswd -c /etc/nginx/htpasswd.users webappdev
```

update default site to match the default file in the kibana folder

`sudo service nginx restart`