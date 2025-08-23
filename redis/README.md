# Platform As A Service of Redis

- Run Redis in docker

- The project can be used in development environment

- **Do not use in production environment**

## Prerequisites

- [docker](https://docs.docker.com/install/)
- [Git](https://git-scm.com/)

## Running

```shell
cd redis
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
cd redis
docker compose down
```

### Admin UI

ActiveMQ manage console is listening on 8161, it should be accessible once the container starts up.
[activemq console](http://localhost:8161/)

The default credential is artemis/artemis unless they are specified in the compose file with
```
ARTEMIS_USERNAME=<>
ARTEMIS_PASSWORD=<>
```
## License

This project is licensed under the MIT License - see the [LICENSE.md](https://github.com/shunchaowang/my-platform-docker/LICENSE) file for details.
