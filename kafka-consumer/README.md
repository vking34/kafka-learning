# Consumer


## Group Coordinator
- The group coordinator is nothing but one of __the brokers which receives heartbeats__ (or polling for messages) from all consumers of a consumer group. Every consumer group has a group coordinator.
- If a consumer stops sending heartbeats, the coordinator will trigger a rebalance.

## Group Leader

- Group Leader is the __first consumer__ that joins the group.

- The leader __receives a list of all consumers__ in the group from the group coordinator and is responsible for __assigning a subset of partitions to each consumer__. It uses an implementation of PartitionAssignor to decide which partitions should be handled by
which consumer.

- After deciding on the partition assignment, the consumer leader __sends the list of assignments to the GroupCoordinator__ which sends this information to all the consumers. __Each consumer only sees his own assignment__ - the leader is the only client process that has the full list of consumers in the group and their assignments. __This process repeats every time a rebalance happens__.

## Notes

- When implementing a __multi-threaded__ consumer architecture, it is important to note that the Kafka consumer is __not thread safe__. Multi-threaded access must be properly synchronized, which can be tricky. This is why the __single-threaded model is commonly used__.

- The only exception to this rule is `wakeup()`, which can safely be used from an external thread to interrupt an active operation. In this case, a `WakeupException` will be thrown from the thread blocking on the operation. This can be __used to shutdown the consumer from another thread__.

## References

- https://www.confluent.de/blog/kafka-consumer-multi-threaded-messaging/