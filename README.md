# Spring Boot Kafka Demo

## Overview
This is a simple Spring Boot application demonstrating Kafka mechanisms, including message production and consumption using Kafka.

## Features
- **Kafka Producer:** Sends messages to a Kafka topic.
- **Kafka Consumer:** Listens to the Kafka topic and processes messages asynchronously.
- **REST API:** Provides an endpoint to trigger the Kafka producer.
- **Kafka Configuration:** Uses application properties for configuration.

## Prerequisites
- Java 17 or later
- Apache Kafka 3.8.1
- Zookeeper (required by Kafka)
- Maven 3+

## Installation & Setup

### Step 1: Start Zookeeper and Kafka
Ensure that Zookeeper and Kafka are running before starting the application.

```sh
# Start Zookeeper
zookeeper-server-start.sh config/zookeeper.properties

# Start Kafka
kafka-server-start.sh config/server.properties
```

### Step 2: Clone the Repository
```sh
git clone https://github.com/your-repo/springboot-kafka-demo.git
cd springboot-kafka-demo
```

### Step 3: Build and Run the Application
```sh
mvn spring-boot:run
```

## API Usage

### 1. Send a Message to Kafka
```sh
curl -X POST http://localhost:8080/kafka/send/HelloKafka
```

### 2. Kafka Consumer Logs Message
Check the console logs for message consumption output.

## Configuration
Edit `application.properties` or `application.yml` for custom configurations.

Example:
```properties
spring.kafka.bootstrap-servers=localhost:9092
spring.kafka.consumer.group-id=group_id
```

## Troubleshooting
If Kafka is not reachable:
1. Ensure Kafka is running (`kafka-server-start.sh`)
2. Check port conflicts (`netstat -an | grep 9092`)
3. Verify consumer and producer configurations

