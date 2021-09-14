# Streams

## ksqlDB - Create Stream

```sql
create stream orders_stream (orderId int, product VARCHAR)
   WITH (KAFKA_TOPIC='streaming.orders.input', VALUE_FORMAT='JSON');

SET 'auto.offset.reset'='earliest';

select * from orders_stream emit changes;

confluent local services status
confluent local services start
confluent local services ksql-server start

```

## KSQL Command Line

### Create a topic

```bash
kafka-topics --bootstrap-server localhost:9092 --create --partitions 1 --replication-factor 1 --topic USERS
```

## Process Unbounded and Bounded Data

Any kind of data is produced as a stream of events. Credit card transactions, sensor measurements, machine logs,
or user interactions on a website or mobile application, all of these data are generated as a stream.

Data can be processed as unbounded or bounded streams.

## Unbounded streams

Unbounded streams have a start but no defined end. They do not terminate and provide data as it is generated.
Unbounded streams must be continuously processed, i.e., events must be promptly handled after they have been ingested.
It is not possible to wait for all input data to arrive because the input is unbounded and will not be complete at any point in time.
Processing unbounded data often requires that events are ingested in a specific order, such as the order in which events occurred, to be able to reason about result completeness.

## Bounded streams

Bounded streams can be processed by ingesting all data before performing any computations.
Ordered ingestion is not required to process bounded streams because a bounded data set can always be sorted. Processing of bounded streams is also known as batch processing.
