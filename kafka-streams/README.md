# Kafka Streams

## Operations


## Join Operations

- KStream + KTable + Inner Join = KStream 

## Types of Windows

- __Tumbling time window__ (time-based): Fixed-size, non-overlapping, gap-less windows.

- __Hopping time window__ (time-based): Fixed-size, overlapping windows.

- __Sliding time window__ (time-based): Fixed-size, overlapping windows that work on differences between record timestamps.

- __Session window__ (session-based): Dynamically-sized, non-overlapping, data-driven windows.


## References

- https://www.confluent.io/blog/crossing-streams-joins-apache-kafka/