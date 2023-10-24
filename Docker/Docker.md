#### Basic commands

##### pull service

`docker-compose pull (service)`

##### turn off services

`docker-compose down (service)`

##### Remove container

`docker volume rm (volume_name)`

##### turn on services with force recreate

`docker-compose up --force-recreate --build -d`

#### Remove stopped containers

`docker container prune`

#### Remove dangling images (unused images)

`docker image prune`

#### Container build from local source with argument

##### Through command

`docker build -t project/frontend-local:master . --build-arg=MY_API_URL=https://www.my-api.fr/api`

##### Through (gitlab) pipeline

```
Key AUTO_DEVOPS_BUILD_IMAGE_EXTRA_ARGS
Value --build-arg=MY_API_URL=https://www.my-api.fr/api
```

#### Nginx build timeout fix

```bash
export DOCKER_CLIENT_TIMEOUT=120
export COMPOSE_HTTP_TIMEOUT=120
```
