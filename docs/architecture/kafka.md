# Kafka

The main purpose of Kafka is to decouple source and target systems so that we simplify integrations

## Kafka Use Cases

- Messaging
- Activity Tracking
- Metrics & Log Gathering
- Stream Processing (Stram API or Spark)
- Decouple Systems
- Integration with Spark, Flink, Storm, Hadoop and other Big Data technologoes.

## Essentials

- a Kafka Topic is split into **Partitions** (0, 1, 2 ...etc)
- Each Partition is Ordered
- Each message in a Partition gets an incremental id, called offset.
- Offset has a meaning within a Partition
- Order is guaranteed only within a Partition
- Data is kept for a limited time (default 1 week)
- **Once a data is written to a partition, it cannot be changed. (Immutability)**
- Data is assigned randomly to a partition unless a key is provided.
