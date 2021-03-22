#ELK deploy for win10


## Initialize ELK

# 1.Download Elasticsearch

https://www.elastic.co/cn/downloads/elasticsearch

# 2.Download Kibana

https://www.elastic.co/cn/downloads/kibana

# 3.Download Logstash

https://www.elastic.co/cn/downloads/logstash

## Remark:ELK preferably the same version

# Install JAVA jdk and configure JAVA environment

https://www.oracle.com/java/technologies/javase-jdk16-downloads.html

https://www.runoob.com/w3cnote/windows10-java-setup.html

## Config ELK

# 1.Config Kibana

open '../kibana/config/kibana.yml'

i18n.locale: "zh-CN"

elasticsearch.hosts: ["http://localhost:9200"]

# 2.Config logstash

open  '../logstash/bin/'

create 'logstash_{your index name}.conf' like 'logstash_nerotest.conf'

content:please For more information, see the config folder.

# 3.Run elasticsearch and create index

..\bin\elasticsearch.bat

Use postman to create index(must low case)

[PUT]http://localhost:9200/nerotest

# 4.Run kibana and check your index

..\bin\kibana.bat

open http://localhost:5601/ and check your index

# 5.Run logstash

prepare log please For more information, see the logfile folder.

..\bin\cmd

print 'logstash -f logstash_nerotest.conf'
