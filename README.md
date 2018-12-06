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


## docker run command

```docker run -i mmussa/afjas-sfac-ass``` giving the flag of -i allows to use input prompt.

```docker run -d mmussa/afjas-sfac-ass``` giving the flag of -d allows to run the container in a background mode.

```docker run -p 80:5000 mmussa/afjas-sfac-ass``` allows you to map the port of the internal docker host with the browser outside the host. This is very useful when you're running differents applications.

#### Persisiting data into our containers

```docker run -v /opt/datadir:/var/lib/mysql mysql``` this make use of volumes for persisting data.

```docker attach lkjali323fa ``` brings you back the process of a container was in background.


 ## Creating a Dockerfile

 DockerFile

Instruction  | Argument
------------ | -------------
FROM | Ubuntu
RUN | apt-get update
RUN | apt-get install python
RUN | pip install flask
RUN | pip install mysql
COPY | . /opt/source-code
ENTRYPOINT FASK_APP= | /opt/source-code/app.py flask run

#### Creating our image

```docker buid dockerfile -t billiramirez/my-custom-app``` It creates a layered architecture. Each layer is a command.

apt-get update
apt-get install python
apt-get install python-pip
pip install flask
/opt/app.py

FLASK_APP=/opt/app.py flask run --host=0.0.0.0



