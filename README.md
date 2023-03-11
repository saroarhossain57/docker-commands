# docker-commands

👉 To see details of any command attach ` --Help `

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

