# kafka-elk
### Containers up
    docker-compose up

![Infra](infra.PNG)

### del containers
    docker-compose down

### containers
    # list all containers
    docker ps -a

    # enter 
    docker exec -it xxxxxxxx bash

### elastic.co
https://www.docker.elastic.co/

###### Broker(Cluster)
2888/tcp, 0.0.0.0:2181->2181/tcp, 3888/tcp                 zookeeper
0.0.0.0:9092->9092/tcp                                     kafka
0.0.0.0:9000->9000/tcp                                     kafka-manager

###### Indexer
0.0.0.0:7777->7777/tcp, 5044/tcp, 0.0.0.0:9600->9600/tcp   kafka-elk_logstash_1

###### Server Side nginx
0.0.0.0:80->80/tcp                                         ng1
kafka-elk_filebeat1_1

0.0.0.0:81->80/tcp                                         ng2
kafka-elk_filebeat2_1


###### Storage and Search(Cluster)
0.0.0.0:9200->9200/tcp, 9300/tcp                           es1
0.0.0.0:5601->5601/tcp                                     kibana
0.0.0.0:5000->5000/tcp                                     elasticsearch-hq-330