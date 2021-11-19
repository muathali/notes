# Data Migration and Initial Load

In a typical Microservices architecture, business applications consume data streamed into various Kafka topics, however it is often the case that these apps would initially need to replicate a specific master data set, for example, a mailer application would need a complete set of employees to seed its local employee table.

There are few ways to replicate an initial data set: AWS Data Migration Service, AWS Glue, also Kafka can be used to stream the initial data set to the target data store.

## AWS Data Migration Service

AWS DMS is a managed service design to migrate databases to AWS, the source database remains fully operational during the migration.

### Benefits

- Simple to Use, AWS Database Migration Service is simple to use. There is no need to install any drivers or applications, and it does not require changes to the source database in most cases. You can begin a database migration with just a few clicks in the AWS Management Console. Once the migration has started, DMS manages all the complexities of the migration process including automatically replicating data changes that occur in the source database during the migration process. You can also use this service for continuous data replication with the same simplicity
- Supports widely used databases, AWS Database Migration Service can migrate your data to and from most of the widely used commercial and open source databases. It supports homogeneous migrations such as Oracle to Oracle, as well as heterogeneous migrations between different database platforms, such as Oracle to Amazon Aurora. Migrations can be from on-premises databases to Amazon RDS or Amazon EC2, databases running on EC2 to RDS, or vice versa, as well as from one RDS database to another RDS database. It can also move data between SQL, NoSQL, and text based targets
- Low cost, AWS Database Migration Service is a low cost service. You only pay for the compute resources used during the migration process and any additional log storage. Migrating a terabyte-size database can be done for as little as $3. This applies to both homogeneous and heterogeneous migrations of any supported databases.
- For additional information and to get started using the service, see [AWS Database Migration Service](https://aws.amazon.com/dms/) on the web.

## AWS Glue

AWS Glue is a serverless data integration and ETL service, it provides capabilities needed for data integration so that you can start analyzing your data quickly. Glue uses ETL jobs that are Scala or Python based and works on top of the Apache Spark environment to provide a scale-out execution environment for your data transformation jobs, for simple data load tasks that does not require extensive transformation AWS DMS might be a simpler, lower cost and better choice.

## Kafka Replication Topic

A separate Kafka replication topic can be created for the purpose of seeding the target data set, this approach might clutter the Kafka cluster as it really not meant to stream data, care must be taken to remove this topic when it is no longer needed.

## Replay Source Data Set

To replicate the initial data set, one can re-play all records from the source database to the main kafka topic, however this approach is not recommended as it requires that other consumers are able to handle the extra traffic gracefully, in addition it creates an illusion of new events that did not really happen but was manufactured in order to move the data.
