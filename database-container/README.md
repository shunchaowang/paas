# my Platform As A Sservice of database containers

- Run PostgreSQL, MySQL, MongoDB, Redis in docker

- The project can used in development environment

- **Do not use in production environment**

## Prerequisites

- [docker](https://docs.docker.com/install/)
- [Git](https://git-scm.com/)

## Running

```shell
cd database-container
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
docker exec -it <container_id> bash
```

## Stopping

```shell
cd database-container
docker compose down
```

## Databases username and password

| database | username | password |
| :------: | :------: | :------: |
|  mysql   |   root   |   root   |
|  mongo   |    /     |    /     |
|  redis   |    /     |    /     |
| postgres |   user   |   pass   |

### Access mysql

- I use DBeaver to connect to the mysql when docker is up

- mysql cli to access

```
mysql -h 127.0.0.1 -u root -p
```

if the db in MYSQL_DATABASE is not created when docker is up, make sure `./data/mysql` is empty

### Access mongo

I use mongo compass to access mongo when docker is up

### Access redis

Redis Insight is a management ui for the redis service, once the container starts, the redis insight
should be running on
[redis insight](http://localhost:8001/)

### Access postgres

- use postgres sql command line to access the database

```
psql -h localhost -p 5432 -U user -d postgres
```

if the authentication fails, it could be the credential changes after the volume is created, delete the ./data/postgres and rerun `docker compose up -d` to regenerate the data volume

- use pdadmin dashboard to access the database

#### access the postgres using the cli on the host machine

once the docker compose is up, make sure the host has postgresql client installed, if not install it from the homebrew `brew install postgresql`

the port map is host:container, so 5432:5432 means we have local 5432 port mapped to the 5432 port in the container

```shell
# connect to the postgres db with username of user
psql -h localhost -p 5432 -U user -d postgres
# put the password in the compose file when prompt
# list all dbs
\l
# exit
\q

```

#### access the postgres using the pdadmin ui in the container

open `http://localhost:5050` on the host browser, put in the admin email and password to login
Once login click the 'Add New Server', then under the `Connection` tab, put in the info below:
Host name/address: <get the ip by running `docker inspect postgres_container`>
Port: 5432
Username: postgres
Password: <password_from_the_compose_file>
finally 'Save

## License

This project is licensed under the MIT License - see the [LICENSE.md](https://github.com/shunchaowang/my-platform-docker/LICENSE) file for details.
