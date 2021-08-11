# Kafka Connect

## What Is Kafka Connect?

- Simplify and improve get data in and out of Kafka

- Achieve Fault Totlerance, Exactly Once, Distribution, Ordering (by other programmers)

#
## Kafka Connect Architecture Design
![](../img/kafka-connect-design.png)

## Fundamental Concepts

### Connector

- Kafka Connect Cluster has multiple loaded Connectors

- Each connector is a re-usable piece of code (java jars)

- Many connectors exists in the open source world.

### Task

- Task = Connector + __User Configuraton__

- A Task is linked to connector configuration

- A job configuration may spawn multiple tasks

### Worker

- Worker executes tasks

- A worker is a single process

- A worker can be standalone or in a cluster

### Standalone Mode

- A single process runs your connectors and tasks

- Configuration is bundled with your process

- Very easy to get started with, useful for development and testing

- Not fault tolerant, no scalability, hard to monitor

### Distributed Mode

- Multiple workers run your connectors and tasks

- Configuration is submitted using a REST API

- Easy to scale, and fault tolerant (rebalancing in case a worker dies)

- Useful for production deployment of connectors



