# spring-kafka-webapp


## Build jar

To build image follow the [tuto](https://docs.aws.amazon.com/lambda/latest/dg/java-create-jar-pkg-maven-and-eclipse.html)
whitout the step 5

## Kafka address and topics

To modify the kafka address and topics go to the file located in resources/application.properties

## Local execution

After build

```
java -jar <jar_name>
```

## Docker

To build the docker image after build the jar copy the jar inside the docker folder and execute the command

```
docker build --build-arg JAR_FILE=<jar_name> -t kastellanos/webapp:1.0 .
docker run ...
```

## Kubernetes

To execute on kubernetes. Use the deployment and service yaml's

**don't forget to modify the image name in deployment file if needed**


## Testing

The app sends the info to topicA so to test it execute a command like that

```
~/kafka/bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic topicA --from-beginning
```

And receive information from livetemperature topic

So to the the Results page send info like that

```
echo [{\"uno\":\"dos\"}] | ~/kafka/bin/kafka-console-producer.sh --broker-list localhost:9092 --topic livetemperature > /dev/null
```
