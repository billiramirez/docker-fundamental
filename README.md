# docker-fundamental
Docker fundamental

#### Docker Commands


```
docker run ubuntu
```
* Run the container from a image 
* If the image is not available locally it will pull it out from the repository.
* in order to pull it out you need internet


```
docker ps
```
* basic information about the images: containerid, command, created, etc.

```
docker ps -a 
```

* all the running succeded containers.
```
docker stop silly_image
```

* stop the container, you need to provide the container id or the name.
* you'll see the name of the container.
* then if you run ``` docker ps ``` you're not longer see the  container running.
* but if you run ```docker ps -a``` you'll see the docker container exited successfully.
* it still saved in the disk.

```
 docker rm silly_image
```
* In order to remove the image for real.
* run ```docker ps``` and you're not longer see the image.

```
 docker images
```
* See all the local images, even the ones we pull out from docker hub.

```
 docker rmi ubuntu
```
* remove the docker container.
* but first you need to delete the dependent containers of the image.

```
    docker pull ubuntu
```
* pull an image.

#### Exec Command

```exec``` command is use when you need to write a command for an specific running container, you only need to write: ```docker exec silly_image cat /etc/hosts```.






