# GCP Kafka Consumer

This repo contains example code to consume a Kafka topic with protobuf encoded messages

## First time here?
To make sure you have a fresh build, clean up and build.
```
./gradlew clean build
```


## Running your Beam code
Beam is platform agnostic and can be run using Gradle on a multitude of platforms using Runners. The DirectRunner runs on your machine and thinks it interacts with a cluster of one machine. The DataFlowRunner puts your code on GCPs DataFlow and runs it there.

## Running your Beam code locally
```
./gradlew run
```

The [Gradle build](./build.gradle.kts) file adds some default arguments (a runner and GCP project) for convenience.

## Running your Beam code on GCP
```
./gradlew run --args="--runner=DataflowRunner --project=<...> --subnetwork=<...> --region=<...> --consumerGroup=<...> --storagePrefix=<...> --protobufValueClass=<...> --protobufKeyClass=<...>"
```
If you want to run your Consumer on DataFlow in GCP you will have to specify the runner type, the project and the region.