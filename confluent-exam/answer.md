# Answers

## Producer

- Your producer is producing at a very high rate and the batches are completely full each time. How can you improve the producer throughput ?

    - Answers:
        - Enable compression
        - Increase ```batch.size```

    - Explain:
        - ```batch.size``` controls how many bytes of data to collect before sending messages to the Kafka broker. Set this as high as possible, without exceeding available memory.
        - Enabling compression can also help make more compact batches and increase the throughput of your producer. 
        - ```linger.ms``` will have no effect as the batches are already full

- What is the risk of increasing max.in.flight.requests.per.connection while also enabling retries in a producer?
    - Answer:
        - Message order not preserved

    - Explain:
        - 

## Zookeeper

- A Zookeeper ensemble contains 3 servers. Over which ports the members of the ensemble should be able to communicate in default configuration? (select three)
    - Answer
        - 2181
        - 3888
        - 2888

    - Explain:
        - 2181: client port
        - 2888: peer port
        - 3888: leader port

## Kafka Connect
- What isn't an internal Kafka Connect topic?

    - Answer:
        - connect-jars

- You are using JDBC source connector to copy data from 2 tables to two Kafka topics. There is one connector created with max.tasks equal to 2 deployed on a cluster of 3 workers. How many tasks are launched?
    - Answer:
        - 2
    
    - Explain:
        - Take the lower ```max.tasks``` and the number of tables

- 

## CLI

- How will you find out all the partitions where one or more of the replicas for the partition are not in-sync with the leader?

    - Answer:
        - kafka-topics.sh --zookeeper localhost:2181 --describe --under-replicated-partitions

