# Kafka cluster migration

The source Kafka cluster (localhost:9092) will be migrated to the target Kafka cluster (localhost:9094).

## Run
export KAFKA_HOME=/Users/chiodonia/Downloads/kafka_2.13-3.0.0

${KAFKA_HOME}/bin/zookeeper-server-start.sh ./source-zookeeper.properties
${KAFKA_HOME}/bin/kafka-server-start.sh ./source-server.properties

${KAFKA_HOME}/bin/zookeeper-server-start.sh ./target-zookeeper.properties
${KAFKA_HOME}/bin/kafka-server-start.sh ./target-server.properties

${KAFKA_HOME}/bin/connect-mirror-maker.sh ./mm2.properties

## Literature
https://www.instaclustr.com/blog/kafka-mirrormaker-2-theory/