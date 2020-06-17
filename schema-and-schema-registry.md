# Schema and Schema Registry  
- Kafka takes bytes and publish them, it doesnt validate the message or its type so no data verification.
So if producer changes some data consumer will fail to convert bytes to data. 
Therefore there should be some service and registry to define data type e.g. Confluent Schema Registry and Apache Avro to define data format
- Kafka broker should not veryfy message they recieve since its not their responsibility and it will slow kafka.
- In producer props we provide schema registry url config  
- In gradle/pom we provide kafka-schema-registry-client and kafka-avro-serializer dependencies  
- Value serializer io.confluent.kafka.serializers.KafkaAvroSerializer  
- Used Avro maven plugin in example.  
- Used default field in existing avro schema to prevent from breaking existing producer consumer.  

# Avro
- New type of data format. Like csv (no schema), db (have schema but has to be flat in row and column), json (no schema/typed).  
- Avro is defined by schema which is written in json  
- Its like json having schema attached to it.
- Data is typed and compressed automatically.  
- Cant print without avro tools since its compressed and serialized.
- Avro tool to generate code of Avro schema  
java -jar avro-tools-1.8.1.jar compile schema Report.avsc  generates Report.java
