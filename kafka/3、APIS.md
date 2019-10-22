# 3、APIS

### 设置

> 需要设置，否则java api发不出信息也接收不到信息

```shell
> vi config/server.properties

advertised.listeners=PLAINTEXT://your.ip:9092

```

### maven

```java
<dependency>
    <groupId>org.apache.kafka</groupId>
    <artifactId>kafka-clients</artifactId>
    <version>2.3.0</version>
</dependency>
```

### producer

```java
public class KafkaProducerApp {

    public static void main(String[] args) throws ExecutionException, InterruptedException {
        Properties props = new Properties();
        props.put("bootstrap.servers", "192.168.137.132:9092");
        props.put("acks", "all");
        props.put("key.serializer", "org.apache.kafka.common.serialization.StringSerializer");
        props.put("value.serializer", "org.apache.kafka.common.serialization.StringSerializer");

        Producer<String, String> producer = new KafkaProducer<>(props);


        producer.send(new ProducerRecord<String, String>("foo", "k", "v"));
        producer.close();

    }

}
```

### consumer

```java
public class KafkaConsumerApp {

    public static void main(String[] args) {
        Properties props = new Properties();
        props.setProperty("bootstrap.servers", "192.168.137.132:9092");
        props.setProperty("group.id", "test");
        props.setProperty("enable.auto.commit", "true");
        props.setProperty("key.deserializer", "org.apache.kafka.common.serialization.StringDeserializer");
        props.setProperty("value.deserializer", "org.apache.kafka.common.serialization.StringDeserializer");

        KafkaConsumer<String, String> consumer = new KafkaConsumer<String, String>(props);

        consumer.subscribe(Arrays.asList("foo"));

        while (true) {
            ConsumerRecords<String, String> records = consumer.poll(Duration.ofMillis(100));
            for (ConsumerRecord<String, String> record : records) {
                System.out.printf("offset=%s, key=%s, value=%s\n", record.offset(), record.key(), record.value());
            }
        }
    }

}
```

### offset

```java
KafkaConsumer<String, String> consumer = new KafkaConsumer<String, String>(props);

Map<TopicPartition, OffsetAndMetadata> hashMap = new HashMap<>();
hashMap.put(new TopicPartition("foo", 0), new OffsetAndMetadata(0));
consumer.commitSync(hashMap);

consumer.subscribe(Arrays.asList("foo"));
```

- 其中 group.id 是新添加的，则offset可以为任意位置
- 如group.id是已经添加了的，则offset从0开始