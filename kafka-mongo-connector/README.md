# Kafka Connect

Kafka connect is a tool for streaming data between kafka and other systems, it can be used to do the etl between data source and data sink through kafka topics.

Data source -> kafka connect -> kafka -> kafka connect -> data sink

## kafka source connector

## kafka sink connector

# Kafka ecosystemm

## set up

## mongodb kafka connectors

## mongodb source connector

## mongodb sink connector

# data replication & sync

## replication

## sync

# demo

the docker compose file contains the docker setup for the whole ecosystem

## zookeeper

## broker

## schema-registry

## connect

## control-center

## rest-proxy

run `docker compose up -d` to start the docker compose, then the control center should be accessible [control center](http://localhost:9021).
to stop the compose run `docker compose down`
