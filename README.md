# Apache Flink Demo

## Install

Follow the guide https://nightlies.apache.org/flink/flink-docs-release-1.20/docs/try-flink/local_installation/

TL;DR

Make sure you have Java 11 installed

`java --version`

Download the latest binary release of Flink and extract it:
`tar -xzf flink-*.tgz`

Install maven from https://maven.apache.org/install.html

Run Maven script

mvn archetype:generate \
    -DarchetypeGroupId=org.apache.flink \
    -DarchetypeArtifactId=flink-walkthrough-datastream-java \
    -DarchetypeVersion=1.20.0 \
    -DgroupId=frauddetection \
    -DartifactId=frauddetection \
    -Dversion=0.1 \
    -Dpackage=spendreport \
    -DinteractiveMode=false
`

## Demo 1

`git clone https://github.com/garystafford/streaming-sales-generator`

You need Docker on host machine to run this demo

Run `docker compose up` to run Apache Flink stack

See Flink Job manager UI at localhost:8081

## Demo 2

`git clone https://github.com/garystafford/flink-kafka-demo`

`cd flink-kafka-demo`

Build and run flink job

./gradlew clean shadowJar

Copy contents of build to to ${PROJECT_DIR}/jobs
You can run job using Flink Job manager ui or by copying jar to container and running it from there