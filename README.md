# How to create a Kafka consumer WebAPI (with a Hostes Service)

## 1. Prerequisite

### 1.1. Kafka installation

Download Kafka (**kafka_2.13-3.6.1.tgz**) from Apache web page: https://kafka.apache.org/downloads

![image](https://github.com/luiscoco/MicroServices-Kafka_dotNET8_CRUD_WebAPI-Azure-SQL/assets/32194879/3a9121f2-9fe7-4a1f-a386-e91d288dfb94)

We uncompress the **kafka_2.13-3.6.1.tgz** and copy the folder in the C:/

![image](https://github.com/luiscoco/MicroServices-Kafka_dotNET8_CRUD_WebAPI-Azure-SQL/assets/32194879/79cf7efe-6c7f-4be9-925e-02bbad5c3ee1)

![image](https://github.com/luiscoco/MicroServices-Kafka_dotNET8_CRUD_WebAPI-Azure-SQL/assets/32194879/c71fde3b-fa3f-4118-9378-a1f0b36f4fbd)

We create add the **C:\kafka_2.13-3.6.1\bin\windows** in the **PATH** environmental variable

![image](https://github.com/luiscoco/MicroServices-Kafka_dotNET8_CRUD_WebAPI-Azure-SQL/assets/32194879/e2bd5826-a890-451c-a4ae-aaa89fb2dc4c)

![image](https://github.com/luiscoco/MicroServices-Kafka_dotNET8_CRUD_WebAPI-Azure-SQL/assets/32194879/e072ba06-e055-406b-abf4-1d5e0062b0bb)

**VERY IMPORTANT:** Set the **bootstrap_server** in the **server.properties** file

```
advertised.listeners=PLAINTEXT://localhost:9092
```

![image](https://github.com/luiscoco/MicroServices-Kafka_dotNET8_CRUD_WebAPI-Azure-SQL/assets/32194879/fa9f4aaa-6b5e-4d4e-8465-7768d5008d52)

![image](https://github.com/luiscoco/MicroServices-Kafka_dotNET8_CRUD_WebAPI-Azure-SQL/assets/32194879/fb8e761d-57fb-4044-914e-39d1233e9a4c)

![image](https://github.com/luiscoco/MicroServices-Kafka_dotNET8_CRUD_WebAPI-Azure-SQL/assets/32194879/64cd9941-54a3-4456-afca-a9eff0e24b0c)

Run and Test Kafka

In a command prompt window we first **run Zookeper** 

```
zookeeper-server-start C:\kafka_2.13-3.6.1\config\zookeeper.properties
```

In another command prompt window we **run Kafka server**

```
kafka-server-start C:\kafka_2.13-3.6.1\config\server.properties
```

We **create a topic**

```
kafka-topics --create --partitions 1 --replication-factor 1 --topic test --bootstrap-server localhost:9092
```

We **creata a producer**

```
kafka-console-producer --topic test --bootstrap-server localhost:9092
```

We **create a consumer**

```
kafka-console-consumer.bat --topic test --from-beginning --bootstrap-server localhost:9092
```

We input a message in the Producer prompt and we get it in the consumer prompt, see this picture

![image](https://github.com/luiscoco/MicroServices-Kafka_dotNET8_CRUD_WebAPI-Azure-SQL/assets/32194879/e3524cac-6602-4705-817e-edbc966a68d1)

**IMPORTANT NOTE**: in case you you get an error when you run the Kafka server go to the C:/tmp directore and **delete** the subdirectories **kafka-logs** and **zookeeper**

![image](https://github.com/luiscoco/MicroServices-Kafka_dotNET8_CRUD_WebAPI-Azure-SQL/assets/32194879/a2fdb38c-8d30-48e5-bfd2-dacb751709f5)



