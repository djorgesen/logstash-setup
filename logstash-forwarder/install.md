from logstash server
```shell
scp /etc/pki/tls/certs/logstash-forwarder.crt user@client_server_private_address:/tmp
```
to move the cert to the new server

on webserver
```shell
echo 'deb http://packages.elasticsearch.org/logstashforwarder/debian stable main' | sudo tee /etc/apt/sources.list.d/logstashforwarder.list

wget -O - http://packages.elasticsearch.org/GPG-KEY-elasticsearch | sudo apt-key add -

sudo apt-get update
sudo apt-get install logstash-forwarder

sudo mkdir -p /etc/pki/tls/certs
sudo cp /tmp/logstash-forwarder.crt /etc/pki/tls/certs/

```

see example logstash-forwarder.conf file in this folder.