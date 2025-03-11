# pacmann-kafka-course
Short course on how to setup Kafka, create topics, and basic Kafka stuffs

## How to start Kafka

1. Go to `kafka/` directory
2. Run `./bin/zookeeper-server-start.sh config/zookeeper.properties`
3. Run `./bin/kafka-server-start.sh config/server.properties`

## Create a topic
Run `./bin/kafka-topics.sh --bootstrap-server <host>:<port> --create --topic {topic_name}`
For multiple topics, consider using Kubernetes or Terraform. One way to do it is probably like [this](https://stackoverflow.com/questions/43115759/how-to-create-a-list-of-topics-in-apache-kafka-using-single-command) 

## Delete topic(s)
Run `./bin/kafka-topics.sh --bootstrap-server <host>:<port> --delete --topic {topic_name}`
Run `./bin/kafka-topics.sh --bootstrap-server <host>:<port> --delete --topic {topic_name_1},{topic_name_2}`

## List topics
Run `./bin/kafka-topics.sh --bootstrap-server <host>:<port> --list`

## Send message(s) to a topic
1. Run `./bin/kafka-console-producer.sh --bootstrap-server <host>:<port> --topic {topic_name}`
2. Input the message(s)

## Read message(s) from a topic
Run `./bin/kafka-console-consumer.sh --bootstrap-server <host>:<port> --topic {topic_name} --from-beginning`
