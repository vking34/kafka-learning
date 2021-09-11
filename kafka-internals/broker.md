# Broker


## Quotas

- Kafka cluster has the ability to __enforce quotas on requests to control the broker resources used by clients__. Kafka provides a mechanism to override quotas at client level without any restart.

- An example to configure client with id "test_client" with producer quota as 10 MB and consumer quota as 20 MB:
    ```
    bin/kafka-configs.sh --zookeeper localhost:2181 --alter --add-config 'producer_byte_rate=10485760,consumer_byte_rate=20971520' --entity-name test_client --entity-type clients
    ```
