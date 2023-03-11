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