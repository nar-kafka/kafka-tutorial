
## Resources
- Quick Start  
https://kafka.apache.org/quickstart

## Quick Start
`cd D:\Soft\MessagingQueue\kafka_2.12-2.3.1`

- Start Zookeeper  
`bin\windows\zookeeper-server-start.bat config\zookeeper.properties`

- Start Kafka  
`bin\windows\kafka-server-start.bat config\server.properties`

- Create Topic  
`bin\windows\kafka-topics.bat --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 --topic test`  
`bin\windows\kafka-topics.bat --create --bootstrap-server localhost:9092 --replication-factor 3 --partitions 1 --topic my-replicated-topic`

- List Topic  
`bin\windows\kafka-topics.bat --list --bootstrap-server localhost:9092`

- Describe Topic (To see which broker is doing what)  
`bin\windows\kafka-topics.bat --describe --bootstrap-server localhost:9092 --topic my-replicated-topic`

- Console producer  
`bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic test`  
`bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic my-replicated-topic`

- Console Consumer  
`bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic test --from-beginning`  
`bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic my-replicated-topic --from-beginning`

- Delete Topic  
`bin/kafka-topics.sh --zookeeper localhost:2181 --delete --topic topic_name`

- Modify  
`bin/kafka-topics.sh --zookeeper localhost:2181 --alter --topic Hello-kafka --parti-tions 2`

- Get Process Id  
`wmic process where "caption = 'java.exe' and commandline like '%server-1.properties%'" get processid`  
`taskkill /pid 6016 /f`

- Kafka Connect import export data  
`bin\windows\connect-standalone.bat config\connect-standalone.properties config\connect-file-source.properties config\connect-file-sink.properties`

- Test URL  
http://localhost:8080//springboot-kafka/producer?message=test
