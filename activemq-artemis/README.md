# Platform As A Service of ActiveMQ Artemis

- Run ActiveMQ in docker

- The project can be used in development environment

- **Do not use in production environment**

## Prerequisites

- [docker](https://docs.docker.com/install/)
- [Git](https://git-scm.com/)

## Running

```shell
cd kafka-cluster
docker compose up -d

# show docker-compose log
docker compose logs -f

# show docker process
docker ps

# show all docker process
docker ps -a
```

## To get into the container shell

```shell
# list all running containers
docker ps

# use the container id from the ps
docker exec <container_id> -it bash
```

## Stopping

```shell
cd kafka-cluster
docker compose down
```

## Kafka

the docker container has 3 components, 3 kafka brokers, 1 zookeeper and 1 ui to access the system

### Brokers

all 3 brokers are configured the same way with different ports since they are running in the same container and host
the 3 brokers communicate using the advertised listeners configured
all brokers connect to the zookeeper on 2181

- kafka1 advertised listen on port 9092 internally and 29092 externally
- kafka2 advertised listen on port 9093 internally and 29093 externally
- kafka3 advertised listen on port 9094 internally and 29094 externally

### Zookeeper

zookeeper listens on 2181 and the port 2181 is mapped externally

### Kafka UI

kafka ui listens on 8080 internally and maps to 8085 externally and is accessible on 8085 from the host
the ui has a local cluster with bootstrap servers of the 3 kafka brokers
to access the ui once the docker container is up

```
curl http://localhost:8085
```

## License

This project is licensed under the MIT License - see the [LICENSE.md](https://github.com/shunchaowang/my-platform-docker/LICENSE) file for details.
