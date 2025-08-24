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

### Redis Insight

Redis Insight is a management ui for the redis service, once the container starts, the redis insight
should be running on
[redis insight](http://localhost:8001/)

## License

This project is licensed under the MIT License - see
the [LICENSE.md](https://github.com/shunchaowang/my-platform-docker/LICENSE) file for details.
