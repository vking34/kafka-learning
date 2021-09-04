# Producer

## Configs

### Performance Configs

- `compression.type`: Producers usually send data that is text-based, for example with JSON data. In this case, it is important to apply compression to optimize for throughput. Compression is more effective the bigger the batch of messages being sent to Kafka. Possible values are: __`lz4` (recommended for performance)__, `snappy`, `zstd`, `gzip`.

- `batch.size`: With batching strategy of Kafka producers, you can batch messages going to the same partition, which means they collect multiple messages to send together in a single request. The most important step you can take to __optimize throughput__ is to tune the producer batching to increase the batch size and the time spent waiting for the batch to populate with messages. Larger batch sizes result in fewer requests, which reduces load on producers and the broker CPU overhead to process each request.

- `linger.ms`: It's the number of milliseconds a producer is willing to wait before sending a batch out (defaults to 0). By introducing some lag, we increase the changes of messages being sent together in a batch. If the batch is full (batch.size) before the end of linger.ms period, it will be sent to Kafka right away.

## Commands
- https://docs.confluent.io/platform/current/tutorials/examples/clients/docs/kafka-commands.html#produce-records