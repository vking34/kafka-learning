# Kafka Operations


## Resources

- Kafka relies heavily on the filesystem for storing and caching messages. All data is immediately written to a persistent log on the filesystem without necessarily flushing to disk. In effect this just means that it is transferred into the kernel's `pagecache`.

- A machine with __64__ GB of RAM is a __decent choice__, but __32__ GB machines are not __uncommon__. Less than 32 GB tends to be counterproductive (you end up needing many, many small machines).