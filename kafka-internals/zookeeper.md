# Zookeeper


## Ensemble

- Min of majority zookeeper nodes: 3

- Zookeeper cluster needs to have an odd number of servers, and must maintain a majority of servers up to be able to vote. Therefore, a 2N+1 zookeeper cluster can survive to N zookeeper be
ing down.


## Information stored in Zookeeper

- ACL info

- Controller registration

- Broker registration
