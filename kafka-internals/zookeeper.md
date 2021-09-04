# Zookeeper

## Definition

- `Zookeeper` is a top-level software developed by Apache that acts as a centralized service and is used to maintain naming and configuration data and to provide flexible and robust synchronization within distributed systems. Zookeeper keeps track of status of the Kafka cluster nodes and it also keeps track of Kafka topics, partitions etc

- Zookeeper's internal data structure is like a tree:

    - Each node is called a zNode

    - Each zNode has a path

    - zNodes can be persistent or ephemeral

    - Each zNode can store data

    - Cannot rename a zNode

    - Each zNode can be watched for changes

- To start `zookeeper` service:
    ```
    bin/zookeeper-server-start.sh config/zookeeper.properties
    ```

## Ensemble

- Min of majority zookeeper nodes: 3

- In a production environment, the ZooKeeper servers will be deployed on multiple nodes. This is called an ensemble. An ensemble is a set of `2n + 1` ZooKeeper servers where n is any number greater than 0. The odd number of servers allows ZooKeeper to perform majority elections for leadership. At any given time, there can be __up to `n` failed servers__ in an ensemble and the ZooKeeper cluster will keep `quorum`. If at any time, `quorum` is lost, the ZooKeeper cluster will go down.

## Information stored in Zookeeper

- ACL info

- Controller registration

- Broker registration
