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

Sample output
```
daopham@Deans-MacM2 kafka-confluent-go % out/producer 
Produced event to topic purchases: key = jsmith     value = gift card
Produced event to topic purchases: key = awalther   value = gift card
Produced event to topic purchases: key = awalther   value = t-shirts
Produced event to topic purchases: key = sgarcia    value = gift card
Produced event to topic purchases: key = awalther   value = book
Produced event to topic purchases: key = jbernard   value = book
Produced event to topic purchases: key = sgarcia    value = book
Produced event to topic purchases: key = sgarcia    value = batteries
Produced event to topic purchases: key = jsmith     value = alarm clock
Produced event to topic purchases: key = eabara     value = batteries
```

Run Consumer
```
out/consumer
```

Sample output
```
daopham@Deans-MacM2 kafka-confluent-go % out/consumer 
Consumed event from topic purchases: key = jsmith     value = gift card
Consumed event from topic purchases: key = awalther   value = gift card
Consumed event from topic purchases: key = awalther   value = t-shirts
Consumed event from topic purchases: key = sgarcia    value = gift card
Consumed event from topic purchases: key = awalther   value = book
Consumed event from topic purchases: key = jbernard   value = book
Consumed event from topic purchases: key = sgarcia    value = book
Consumed event from topic purchases: key = sgarcia    value = batteries
Consumed event from topic purchases: key = jsmith     value = alarm clock
Consumed event from topic purchases: key = eabara     value = batteries
```
