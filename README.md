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

### .env

```bach
GATEWAY_API_PORT=8080
AUTHENTIFICATION_API_PORT=8081
USER_API_PORT=8082
PROJECT_API_PORT=8083
EVENT_API_PORT=8084
LIST_API_PORT=8085
TASK_API_PORT=8086
AUTHENTIFICATION_API=http://authentication_api:8081/auth
USER_API=http://user_api:8082/users
PROJECT_API=http://project_api:8083/projects
EVENT_API=http://event_api:8084/events
LIST_API=http://list_api:8085/lists
TASK_API=http://task_api:8086/tasks
DB_URL=jdbc:mysql://todolist_db:3306/todolistMicroServices
DB_USERNAME=root
DB_PASSWORD=
### this part will not work with the docker-compose
SECRET_TOKEN=token
EMAIL_SENDER=mail
EMAIL_PASSWORD=password

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
