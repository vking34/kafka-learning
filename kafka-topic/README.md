# Kafka Topic

## Configurations

- `log.cleanup.policy`: Options for the cleanup policy are either `delete` or `compact` or both. The string designates the retention policy to use on old log segments. The default policy `delete` will discard old segments when their retention time or size limit has been reached.

## Compacted Topics

- `Log Compaction` ensures that Kafka will always retain at least the last known value for each message key within the log of data for a single topic partition. It addresses use cases and scenarios such as restoring state after application crashes or system failure, or reloading caches after application restarts during operational maintenance.

- Offsets of messages are immutable, they never change. Offsets are just skipped if a message is missing.

- Any consumer that is reading from the tail of a log (most current data) will still see all the messages sent to the topic. There will be __no log compaction at the active segment__. Therefore compaction does __not prevent from duplicate data__.

- Deleted records can still be seen by consumers for a period of "delete.retention.ms".

- Log compaction does not re-order data, it only removes some messages.

## CLI

- `describe`: know the leader for the topic, the broker instances acting as replicas for the topic, and the number of partitions of a Kafka topic
    - `--topics-with-overrides`: If set when describing topics, only show topics that have __overridden configs__.

    - `--unavailable-partitions`: If set when describing topics, only show partitions whose __leader is not available__.

    - `--under-min-isr-partitions`: If set when describing topics, only show partitions whose __ISR count is less than the configured minimum__.

    - `--under-replicated-partitions`: If set when describing topics, only show under replicated partitions. This basically means the cluster is overloaded and followers are not able to catch up on leaders (__not in-sync__).

- `create`:
    - `--if-exists`: If set when altering or deleting or describing topics, the action will only execute if the topic exists.

    - `--if-not-exists`: If set when creating topics, the action will only execute if the topic does not already exist.

## Notes

- If __automatic topic creation is disabled__, `ksqlDB` and `Kafka Streams` applications __continue to work__. They both use the `Admin Client`, so topics are still created.