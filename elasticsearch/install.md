

Ubuntu commands
```bash
sudo add-apt-repository -y ppa:webupd8team/java
sudo apt-get update
sudo apt-get -y install oracle-java8-installer
wget -O - http://packages.elasticsearch.org/GPG-KEY-elasticsearch | sudo apt-key add -
echo 'deb http://packages.elasticsearch.org/elasticsearch/1.4/debian stable main' | sudo tee /etc/apt/sources.list.d/elasticsearch.list

sudo apt-get update
sudo apt-get -y install elasticsearch=1.4.4

sudo update-rc.d elasticsearch defaults 95 10
```

Mod elastic search, set ram to 1gb since 2 gb instance
Find the line with variable `ES_HEAP_SIZE`
set this to 1gb by setting it to 
`ES_HEAP_SIZE=1g`