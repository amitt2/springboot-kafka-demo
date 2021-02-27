## Gradle build
```
> gradlew clean build

```

## Docker build command
docker build -t spring/spring-kafka-demo .

## Tail sping boot app logs
docker logs -f spring-kafka-demo_app_1

## Docker compose command
```
> docker-compose up -d
> docker-compose down

```
## Kafka command
```
> docker-compose exec broker kafka-topics --create --topic users --bootstrap-server broker:29092 --replication-factor 1 --partitions 1

> docker-compose exec broker bash

> kafka-console-consumer --topic users --bootstrap-server broker:9092 

> kafka-console-producer --topic users --broker-list broker:9092
```

## REST API
> curl -X POST -d "message=test" http://localhost:8080/kafka/publish