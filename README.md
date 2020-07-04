# tutorial-microservices-kafka-messaging

<b>Install Kafka </b> <br> 

sudo service zookeeper start <br>
sudo service kafka start <br>
>cd /usr/local/kafka  <br>
> bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic <b>testTopic</b> <br>

<b>Run consumer and producer services:</b></br>
spring.cloud.stream.bindings.input.destination=<b>testTopic</b> (consumer-service properties) <br>
spring.cloud.stream.bindings.output.destination=<b>testTopic</b> (producer-service output topic <br>

<b>Publish from terminal</b> <br>
> curl -X POST --data '{"id": 1, "name": "my message"}' -H "Content-Type:application/json" http://localhost:9192/publish <br>

or from postman <br>

Check message in kafka-console-consumer or spring-cloud-stream-consumer log <br>

> bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic <b>testTopic</b> --from-beginning <br>
or <br>

spring-cloud-stream-consumer console LOG <br>
