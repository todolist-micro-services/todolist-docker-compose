![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)

# Todolist Docker Compose

This repository contain the docker compose ton init a database and start the api.

# How to use

## 1. Docker

You must have [Docker](https://www.docker.com/) on your machine.

## 2. Init

### Default
Create a directory todolist and close this repository inside, the [api repository](https://gitlab.com/todolist-micro-services/todolist-authentification-api) and the [database repository](https://gitlab.com/todolist-micro-services/todolist-database)

```
Note: If you want to change the place of docker-compose.yml, don't forget to chnage these lines in the file:

    - "../todolist-database/app/src/main/java/todolist/database/mysql/init.sql:/docker-entrypoint-initdb.d/1.sql"
    - context: ../todolist-authentification-api
```

## 3. Run

To run all container, use:

```bash
docker-compose up
docker-compose up --build # to build the images
```

If you want to run only selected containers, you can use:
```bash
docker-compose up {CONTAINER_NAME}

# Available container name:
#   - db
#   - authentication_api
```
