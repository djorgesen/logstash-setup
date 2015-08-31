Nxlog is an alternate to either logstash, logstash-forwarder, or both. 

If using just iis logs you can set up nxlog to send logs directly to elasticsearch and you don't
need logstash at all.

In my config, I am using nxlog to parse my iis log format and send it to logstash as json, which I then
mutate as needed. All of this mutation can be done by nxlog on its own, but then I would have
needed to learn 2 config languages, and this seemed better