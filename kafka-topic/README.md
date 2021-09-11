# Kafka Topic

## CLI

- `describe`: know the leader for the topic, the broker instances acting as replicas for the topic, and the number of partitions of a Kafka topic
    - `--topics-with-overrides`: If set when describing topics, only show topics that have __overridden configs__.

    - `--unavailable-partitions`: If set when describing topics, only show partitions whose __leader is not available__.

    - `--under-min-isr-partitions`: If set when describing topics, only show partitions whose __ISR count is less than the configured minimum__.

    - `--under-replicated-partitions`: If set when describing topics, only show under replicated partitions. This basically means the cluster is overloaded and followers are not able to catch up on leaders (__not in-sync__).

- `create`:
    - `--if-exists`: If set when altering or deleting or describing topics, the action will only execute if the topic exists.

    - `--if-not-exists`: If set when creating topics, the action will only execute if the topic does not already exist.

