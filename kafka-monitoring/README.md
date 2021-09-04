# Kafka Monitoring

## Load

### UnderReplicatedPartitions

- The metric `UnderReplicatedPartitions` monitors the number of partitions that have problems with the ISR (in-sync replicas). Replicas that are added as part of a reassignment will not count toward this value. Alert if value is greater than 0.

- `UnderReplicatedPartitions` means that data is not being replicated to enough number of brokers thereby increasing the probability of data loss should those replicas fail or die. If you have under replicated partitions, it typically points to a problem with one or more brokers and you are having a lot of load on the system. You should root cause the problem immediately to avoid any data loss.

## OS

- The Kafka broker uses a __significant amount of processing for handling requests__. For this reason, __keeping track of the CPU utilization is important__ when monitoring Kafka.

- __Memory is less important__ to track for the broker itself, as Kafka will __normally__ be run with a relatively __small JVM heap size__. It will use a small amount of memory outside of the heap for compression functions, but most of the system memory will be left to be used for cache.

- __Disk__ is by far the __most important__ subsystem when it comes to Kafka. __All messages are persisted to disk, so the performance of Kafka depends heavily on the performance of the disks.
    - Monitor usage of both disk space and inodes (inodes are the file and directory metadata objects for Unix filesystems) __not running out of space__. 
    - Monitor the reads and writes per second, the average read and write queue sizes, the average wait time, and the utilization percentage of the disk.

- Monitor the network utilization on the brokers. This is simply the amount of inbound and outbound network traffic, normally reported in bits per second. Keep in mind that __every bit inbound to the Kafka broker will be a number of bits outbound equal to the replication factor of the topics, with no consumers__. Depending on the number of consumers, inbound network traffic could easily become an order of magnitude larger on outbound traffic. Keep this in mind when __setting thresholds for alerts__.