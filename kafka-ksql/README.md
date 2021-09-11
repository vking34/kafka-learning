# Kafka KSQL


## ksqlDB

### Deployments

- `Headless`: The __simplest__ deployment mode for ksqlDB is the headless mode, also called application mode. In the headless mode, you write all of your __queries in a SQL file__, and then __start ksqlDB server instances with this file__ as an argument. Each server instance will __read the given SQL file, compile the ksqlDB statements into Kafka Streams applications__ and start execution of the generated applications. Headless ksqlDB is __recommended for production__ deployments.

- `Interactive`: interact with the ksqlDB servers through a __REST API__ either directly via your __favorite REST clients__, through __ksqlDB CLI__ or through __Confluent Control Center__.

## References

- https://developer.confluent.io/learn-kafka/ksqldb/intro/

- https://docs.confluent.io/4.1.0/ksql/docs/faq.html#is-ksql-fully-compliant-to-ansi-sql