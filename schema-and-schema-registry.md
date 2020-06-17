# Schema and Schema Registry  
- Kafka recieves only bytes and send bytes, it doesnt validate the data or its type.  
So if producer changes some data consumer will fail to convert bytes to data. 
Therefore there should be some service and registry to define data type.
- Kafka broker should not veryfy message they recieve since its not their responsibility and it will slow kafka.
