


Ubuntu commands
```shell
sudo add-apt-repository -y ppa:webupd8team/java
echo 'deb http://packages.elasticsearch.org/logstash/1.5/debian stable main' | sudo tee /etc/apt/sources.list.d/logstash.list
wget -O - http://packages.elasticsearch.org/GPG-KEY-elasticsearch | sudo apt-key add -
sudo apt-get update
sudo apt-get -y install oracle-java8-installer
sudo apt-get install logstash
```
update kibana.yml to point to elasticsearch. it assumes you have elasticsearch locally.

update /etc/ssl/openssl.cnf
to point to the servers ip address in the `[ v3_ca ]` section with the line
`subjectAltName = IP: logstash_server_private_ip`

generate an ssl cert with
```shell
cd /etc/pki/tls
sudo openssl req -config /etc/ssl/openssl.cnf -x509 -days 3650 -batch -nodes -newkey rsa:2048 -keyout private/logstash-forwarder.key -out certs/logstash-forwarder.crt
```

Follow https://www.digitalocean.com/community/tutorials/how-to-install-elasticsearch-logstash-and-kibana-4-on-ubuntu-14-04#configure-logstash
for logstash configuring
