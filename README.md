# Apache Kafka Learning


## 4 Common Kafka Use Cases:

| Use Case | Basic API | Practical Approach|
|----|----|----|
| Source -> Kafka | Producer | Kafka Connector Source|
| Kafka -> Kafka | Consumer + Producer | Kafka Stream|
| Kafka -> Sink | Consumer | Kafka Connect Sink|
| Kafka -> App | Consumer | Consumer |

#
## Knowledge Domains

### Application Design

- Kafka's command line tools

- Pub/Sub and Streaming

- Overall Kafka architecture and design

- Message metadata

- System metrics

- Message Key selection (choices and factors)

- Message schema management

### Development

- Clients: Producer and Consumer, concepts and functions

- Client troubleshooting/debugging

- Performace, throughput, latency, scaling

- Message order and delivery guarantees

- Serialization/Deserialization

- Consumer offset management

- Consumer groups, pertitaion assignment, partition rebalances

- Data retention strategies and implications

- Topic co-partitioning

### Deployment/Testing

- Securing your data

- Monitoring and troubleshooting clients

- Kafka stream features and uses cases
    - Esstential component parts of Kafka Streams application

- KSQL/ksqlDB features and use cases:
    - Esstential elements of KSQL/ksqlDB env


## History

- 2013 - 0.8.x:
    - Topic replication, Log compaction
    - Simplified producer client API

- 2015 - 0.9.x:
    - Simplified high level consumer APIs, without Zookeepeer dependency

    - Added security (Encryption and Authentication)

    - __Kafka Connect APIs__

- 2016 - 0.10.0:
    - __Kafka Streams APIs__

- 2017 - 0.10.1, 0.10.2:
    - __Improved Connect API, Singple Message Transforms API__

## Bonus
- Contact me to:
    - Get more references
    - Get my Udemy account:
        - Courses related to Kafka
        - 6 Confluent exams 