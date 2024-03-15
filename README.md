![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)

# Todolist Docker Compose

This repository contain the docker compose ton init a database and start the api.

# How to use

## 1. Docker

You must have [Docker](https://www.docker.com/) on your machine.

## 2. Init

### Default
Create a directory todolist and clone this repository inside, clone all repository from the [project](https://gitlab.com/todolist-micro-services) in the same directory. 

```
Note: If you want to change the place of docker-compose.yml, don't forget to chnage these lines in the file:

    - "../todolist-database/app/src/main/java/todolist/database/mysql/init.sql:/docker-entrypoint-initdb.d/1.sql" # for the database
    - context: ../todolist-authentification-api # for all other jobs
```

### .env

```bach
CLIENT_PORT=3000
GATEWAY_API_PORT=8080
AUTHENTIFICATION_API_PORT=8081
USER_API_PORT=8082
PROJECT_API_PORT=8083
LIST_API_PORT=8085
TASK_API_PORT=8086
GATEWAY_API=http://localhost:8080
AUTHENTIFICATION_API=http://authentication_api:8081/auth
USER_API=http://user_api:8082/users
PROJECT_API=http://project_api:8083/projects
LIST_API=http://list_api:8085/lists
TASK_API=http://task_api:8086/tasks
DB_URL=jdbc:mysql://todolist_db:3306/todolistMicroServices
DB_USERNAME=root
DB_PASSWORD=
SECRET_TOKEN=asdfSFS34wfsdfsdfSDSD32dfsddDDerQSNCK34SOWEK5354fdgdf4
EMAIL_SENDER=youremail@gmail.com
EMAIL_PASSWORD=
```

If you use gmail like me, you will probably have an error because of the security, you can follow the steps from this [stackoverflow](https://stackoverflow.com/questions/2965251/javamail-with-gmail-535-5-7-1-username-and-password-not-accepted) to generate an application password

On your Google account, enable 2 factors authentication and create an application password.

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
#   - user_api
#   - project_api
#   - list_api
#   - task_api
#   - gateway_api
#   - client
```
