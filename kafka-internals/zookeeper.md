# Zookeeper


## Ensemble

- Min of majority zookeeper nodes: 3

- In a production environment, the ZooKeeper servers will be deployed on multiple nodes. This is called an ensemble. An ensemble is a set of `2n + 1` ZooKeeper servers where n is any number greater than 0. The odd number of servers allows ZooKeeper to perform majority elections for leadership. At any given time, there can be __up to `n` failed servers__ in an ensemble and the ZooKeeper cluster will keep `quorum`. If at any time, `quorum` is lost, the ZooKeeper cluster will go down.

## Information stored in Zookeeper

- ACL info

- Controller registration

- Broker registration
