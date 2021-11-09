# Initial Data Load using Kafka

In a typical Microservices architecture, business applications consume data streamed into various Kafka topics, however it is often the case that these apps would initially need to replicate a specific master data set, for example, a mailer application would need a complete set of employees to seed its local employee table.

There are three possible ways to achieve above requirements, 