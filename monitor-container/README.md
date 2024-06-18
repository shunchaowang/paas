# my Platform As A Sservice of monitor containers

- Run monitor like prometheus and grafana in docker

- The project can used in development environment

- **Do not use in production environment**

## Prerequisites

- [docker](https://docs.docker.com/install/)
- [Git](https://git-scm.com/)

## Running

```shell
cd monitor-container
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
cd monitor-container
docker compose down
```

## Prometheus

Prometheus should be accessible at localhost with port 9090.

```curl http://localhost:9090

```

Note that the target for spring boot app should be using the real ip since prometheus runs in docker.

## Grafana

Grafana is a visualize tool for prometheus, once the platform runs, access localhost:3000, the default credential is admin/admin.

### Configure Prometheus on Grafana

Access grafana at localhost:3000, then add a new Dashboard by clicking 'Add Visualization', put premetheus as the data source, note to use the real ip.

## Get into the container shell

get the docker id by running `docker ps`, then run command to get into the container's shell

```
docker exec -it <container> bash
```

## License

This project is licensed under the MIT License - see the [LICENSE.md](https://github.com/shunchaowang/my-platform-docker/LICENSE) file for details.
