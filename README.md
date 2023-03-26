# docker-commands

👉 To see details of any command attach ` --Help `

### Build an image from Dockerfile
> here . is destination from where I can get the Dockerfile
```
$ docker build . 
```

### Show all running containers
```
docker ps 
```

### Show all containers
```
docker ps -a
```


## Run an image with image ID to build a container from that image.
As we know that container is a copy from image that runs to run the system. So to build an container we always need to run a image. 

> Note: Whenever we will run a image it will always give us a new container.

### It will display all the local images.
```
docker images
```

### It will run the image and build a new container.
```
docker run <image-name>
```

### It will start an old container instead of creating a new continer.
```
docker start <container-name>
```


### Run a new container from image with a given name for container.
```
docker run --name <container-name> <image-name>
```

### run a new docker container with given port for outside world.
```
$ docker run -p 8080:80 <image-name>
```

### Run docker image in detach mode. By default docker run image in attached mode.
```
$ docker run -p 8000:80 -d <image-id>
```
### 😎 You can use below command to start a container in attach mode.
```
$ docker attach <container-name>
```

## 👉 Stop a running container.
```
$ docker stop <container-name>
```

## 👉 When a container is in running mode we can attach it with below command.
```
$ docker attach <container-name>
```

## 👉 To all the logs from a running container use below command.
> Node: use `-f` option to see the logs in attach mode.
```
$ docker logs  <container-name>
```

## Deleting containers and images.

### Remove one or multiple containers
```
$ docker rm <one_or_more_container_names>
```

### ✔🎁 Remove docker images
```
$ docker rmi <image_name>
```

### Automatically remvoe a container when the container is stoped.
```
$ docker run -p 3000:80 -d --rm
```
> `--rm` flag here telling to remove container automatically. 


## Copy from one container to another container. 
```
$ docker cp <copy_folder> <destination_container_name>:<path>
```

## Naming containers and images.
### Give a name to a container 
```
$ docker run -p 3000:80 --name <app_name> <image_name>
```

### Give a name to a already existing image with tag
```
$ docker tag <image_id> <given_name>:<given_tag>
```
> Here we can say given name = `myapp` and tag = `v1.0.0`.

### Give a name to a image while building the image with docker build
```
$ docker build -t <image_name>:<tag> <path_to_dockerfile>
```
Example:
```
$ docker build -t myapp:v1.0.0 .
```

## Docker image push, pull and share etc.
### 👉 Push image to dockerhub repository.
```
$ docker push saroarhossain/mygoals-app:tagname
```
> First always give a same name for local docker image as the dockerhub repository name.
> If you are not logged in from yoru terminal to docker hub then you need to login before push. otherwise it will give us a denied error.

### Login to dockerhub from terminal command
```
$ docker login
```
> It will ask for username and password.

### You can also logout from terminal using below command
```
$ docker logout
```

### Pull a image from dockerhub.

# Docker Volumes
## There is named volume and unnamed volume.
## learn about bind mount volume. because it will be changed while building application.

if we use only volume to store file then we always need to rebuild for any file changes in the source code. But if we bind mount the volume then the container will store the files in our local machine and always pull the codes from our local machine while running so our codes will be always available and the changes will reflect always because the container will call the codes from our local machine whenever it runs inside container.


# Docker NetWorking
## How to call remote APIs.


# Docker compose
## Create compose file
create docker-compose.yaml in root dir

```
version: "3.8"
services: 
    mongodb:
        image: "mongo"
        volumes: 
            - data: /data/db
        environment:
            MONGO_INITDB_ROOT_USERNAME: root
            MONGO_INITDB_ROOT_PASSWORD: pass
    backend:

    frontend

```