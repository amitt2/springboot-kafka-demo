# springboot-kafka-demo
Simple demo springboot application using spring-kafka project to push messages to kafka topic. Using docker compose to start containers for sping boot, kafka broker and kafka zookeeper. 

## Prerequisites
1. Docker
2. Java 1.8+

## Gradle build - to build application jar
```
> gradlew clean build

```

## Docker build command - to create docker image of springboot application
docker build -t spring/spring-kafka-demo .

## Start Docker containers
```
> docker-compose up -d
```

## Tail sping boot app logs
docker logs -f spring-kafka-demo_app_1

## Kafka commands

first create topic named users in kafka.
```
> docker-compose exec broker kafka-topics --create --topic users --bootstrap-server broker:29092 --replication-factor 1 --partitions 1

> docker-compose exec broker bash

> kafka-console-consumer --topic users --bootstrap-server broker:9092 

> kafka-console-producer --topic users --broker-list broker:9092
```

## REST API
> curl -X POST -d "message=test" http://localhost:8080/kafka/publish

## Stop Docker containers
```
> docker-compose down
```