Kafka and Zookeeper in Docker
===

This repository use
```text
    SCALA VERSION 2.11
    KAFKA VERSION 2.0.0
```

Run
```bash
    docker run -d -p 2181:2181 -p 9092:9092 \
		--hostname localhost \
		--env ADVERTISED_HOST=127.0.0.1 \
		--env ADVERTISED_PORT=9092 \
		--name kafkadev chotsiri/kafka
```

Create a topic
```bash
    docker exec kafkadev \
        opt/kafka_[SCALA VERSION]-[KAFKA VERSION]/bin/kafka-topics.sh --create \
        --zookeeper localhost:2181 \
        --replication-factor 1 \
        --partitions 5 \
        --topic test
```

In the box
---
* **chotsiri/kafka**

Public Builds
---
https://hub.docker.com/r/chotsiri/kafka

Build from Source
---

    docker build -t chotsiri/kafka kafka/

Ref
---
* **[spotify/docker-kafka](https://github.com/spotify/docker-kafka)**