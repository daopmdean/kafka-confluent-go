# kafka-confluent-go

Ref: https://developer.confluent.io/get-started/go

## Kafka setup

install Confluent CLI
```
brew install confluentinc/tap/cli
```

Start kafka broker
```
confluent local kafka start
```

After kafka started, it will print out console content such as
```
Status: Downloaded newer image for confluentinc/confluent-local:7.6.0
+-----------------+-------+
| Kafka REST Port | 8082  |
| Plaintext Ports | 57826 |
+-----------------+-------+
Started Confluent Local containers "3f4922d81f".
```

Create a topic named "phurchases"
```
confluent local kafka topic create phurchases
```

When you are done with local kafka
```
confluent local kafka stop
```

## Build 

```
go build -o out/producer cmd/producer/producer.go
```

```
go build -o out/consumer cmd/consumer/consumer.go
```

## Run

Run Producer
```
out/producer
```

Run Consumer
```
out/consumer
```
