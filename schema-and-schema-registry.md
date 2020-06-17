# Schema and Schema Registry  
- Kafka takes bytes and publish them, it doesnt validate the message or its type so no data verification.
So if producer changes some data consumer will fail to convert bytes to data. 
Therefore there should be some service and registry to define data type e.g. Confluent Schema Registry and Apache Avro to define data format
- Kafka broker should not veryfy message they recieve since its not their responsibility and it will slow kafka.
- In producer props we provide schema registry url config  
- In gradle/pom we provide kafka-schema-registry-client and kafka-avro-serializer dependencies
- Value serializer io.confluent.kafka.serializers.KafkaAvroSerializer

# 
