 ELK : [](https://www.javainuse.com/spring/springboot-microservice-elk)
What is ELK? Need for it?
The ELK Stack consists of three open-source products - Elasticsearch, Logstash, and Kibana from Elastic.
Elasticsearch is a NoSQL database that is based on the Lucene search engine.
Logstash is a log pipeline tool that accepts inputs from various sources, executes different transformations, and exports the data to various targets. It is a dynamic data collection pipeline with an extensible plugin ecosystem and strong Elasticsearch synergy
Kibana is a visualization UI layer that works on top of Elasticsearch.
These three projects are used together for log analysis in various environments. So Logstash collects and parses logs, Elastic search indexes and store this information while Kibana provides a UI layer that provide actionable insights.
 
Lets Begin
We will first download the required stack.
Elasticsearch - https://www.elastic.co/downloads/elasticsearch
 

Download the latest version of elasticsearch from Elasticsearch downloads
elasticsearch example : elasticsearch.bat 
 


Run the elasticsearch.bat using the command prompt. Elasticsearch can then be accessed at localhost:9200
Kibana -
Download the latest version of kibana from Kibana downloads
https://www.elastic.co/downloads/kibana
 

Modify the kibana.yml to point to the elasticsearch instance. In our case this will be 9200. So uncomment the following line in kibana.yml-
elasticsearch.url: "http://localhost:9200"
 
Run the kibana.bat using the command prompt. kibana UI can then be accessed at localhost:5601

 


Lagstash:
downaload from :https://www.elastic.co/downloads/logstash
 
When using the ELK stack we are ingesting the data to elasticsearch, the data is initially unstructured. We first need to break the data into structured format and then ingest it to elasticsearch. Such data can then be later used for analysis. This data manipualation of unstructured data to structured is done by Logstash. Logstash itself makes use of grok filter to achieve this.
 


[]([https://www.javainuse.com/spring/springboot-microservice-elk]

Commands: 
elasticsearch.bat 
kibana.bat 
logstash -f logstash.conf

elastic Search API:
GET INDECES:http://localhost:9200/_cat/indices
DELETE: http://localhost:9200/*
Search with index: http://localhost:9200/.kibana_7.17.5_001/_search