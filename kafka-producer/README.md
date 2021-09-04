# Producer

## Configs

### Performance Configs

- `compression.type`: Producers usually send data that is text-based, for example with JSON data. In this case, it is important to apply compression to optimize for throughput. Compression is more effective the bigger the batch of messages being sent to Kafka. Possible values are: __`lz4` (recommended for performance)__, `snappy`, `zstd`, `gzip`.

- `batch.size`: With batching strategy of Kafka producers, you can batch messages going to the same partition, which means they collect multiple messages to send together in a single request. The most important step you can take to __optimize throughput__ is to tune the producer batching to increase the batch size and the time spent waiting for the batch to populate with messages. Larger batch sizes result in fewer requests, which reduces load on producers and the broker CPU overhead to process each request.

- `linger.ms`: It's the number of milliseconds a producer is willing to wait before sending a batch out (defaults to 0). By introducing some lag, we increase the changes of messages being sent together in a batch. If the batch is full (batch.size) before the end of linger.ms period, it will be sent to Kafka right away.

### Others

- `max.block.ms`: the time the `.send()` method will block before throwing an exception. If an exception is thrown this usually means the brokers are down and cannot process any data.

## Commands
- https://docs.confluent.io/platform/current/tutorials/examples/clients/docs/kafka-commands.html#produce-records

## Notes

- If a Kafka producer produces messages faster than the broker can take, the records will be buffered in memory. The default buffer memory is 33554432 bytes (32 MB).

    - The buffer will full up over time and fill back down when the throughput of the broker increases.

    - If the buffer is full, then the .send() method will start to block and won't return right away.