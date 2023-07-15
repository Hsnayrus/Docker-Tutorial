# Docker Tutorial

## Single Image Docker Container: 
* Images are created using Dockerfiles. 
* Clone [this](https://github.com/docker/welcome-to-docker) git repository.
* Open the Dockerfile. This file was pre-created for this project. For your own projects, you will have to create your own. 
* You can build your docker image using this Dockerfile.
* Use the command: `docker build -t welcome-to-docker .` to build your own image. 
    * Here `-t` states that you want to name your image "welcome-to-docker"
    * `.` is the directory in which the Dockerfile can be found. 
* [Run your docker image as a container](https://docs.docker.com/language/nodejs/run-containers/#overview). I used the command: `docker run --publish 3000:3000 welcome-to-docker`
    * The container port is 3000 since the Dockerfile exposes the port 3000 using the command `EXPOSE 3000`
    * It is also recommended to run the container in detached mode, since if you exit the terminal in which you ran the container, the container will shutdown as well. This will result in the command: `docker run --publish 3000:3000 -d welcome-to-docker`
        * Since, you cannot exit the container using `Ctrl+C`, you would now have to manually stop the container which can be done with the command `docker stop <container-id`>, where `<container-id>` is to be replaced with the id of the container. 
        * To find out what your Container ID is, use the command, `docker container ls`, which will give you a list of all the running containers and you can select the relevant one. 
* A container can(usually does) contain multiple images. For example, our Swift Server proejct has an image for the database and an image for the server. 
