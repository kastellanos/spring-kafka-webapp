# spring-kafka-webapp


## Build jar

To build image follow the [tuto](https://docs.aws.amazon.com/lambda/latest/dg/java-create-jar-pkg-maven-and-eclipse.html)
whitout the step 5

## Kafka address and topics

To modify the kafka address and topics go to the file located in resources/application.properties

## Docker

To build the docker image after build the jar copy the jar inside the docker folder and execute the command

```
docker build --build-arg JAR_FILE=<jar_name> -t kastellanos/webapp:1.0 .
docker run ...
```

## Kubernetes

To execute on kubernetes. Use the deployment and service yaml's

**don't forget to modify the image name in deployment file if needed**
