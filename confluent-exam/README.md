# Questions

## Producer

- Your producer is producing at a very high rate and the batches are completely full each time. How can you improve the producer throughput ?

    - Inscrease linger.ms

    - Enable compression

    - Decrease batch.size

    - Disable compression

    - Increase batch.size

    - Decrease linger.ms

## Zookeeper

- A Zookeeper ensemble contains 3 servers. Over which ports the members of the ensemble should be able to communicate in default configuration? (select three)
    - 2181
    - 3888
    - 2888
    - 80
    - 443
    - 9092

## Kafka Connect

- What isn't an internal Kafka Connect topic?

    - connect-jars
    - connect-configs
    - connect-status
    - connect-offsets

- You are using JDBC source connector to copy data from 2 tables to two Kafka topics. There is one connector created with max.tasks equal to 2 deployed on a cluster of 3 workers. How many tasks are launched?
    - 2
    - 3
    - 1
    - 6

- What is the risk of increasing max.in.flight.requests.per.connection while also enabling retries in a producer?

    - Message order not preserved

    - Reduce throughput

    - At least once delivery is not guaranteed

    - Less resilient



## CLI

- How will you find out all the partitions where one or more of the replicas for the partition are not in-sync with the leader?

    - kafka-topics.sh --zookeeper localhost:2181 --describe --unavailable- partitions

    - kafka-topics.sh --bootstrap-server localhost:9092 --describe --unavailable- partitions

    - kafka-topics.sh --broker-list localhost:9092 --describe --under-replicated-partitions

    - kafka-topics.sh --zookeeper localhost:2181 --describe --under-replicated-partitions