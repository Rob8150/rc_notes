## Docker Notes
### run docker as non root

[Run docker without sudo](https://docs.docker.com/engine/install/linux-postinstall/)

### example

#### Install docker

` sudo apt-get install docker.io`

#### Version

`docker --version`

#### Info

`sudo docker info`

#### List images

`docker image ls`

#### pull a container image

`docker image pull ubuntu:latest`

#### Run container in iteractive mode -it

`docker container run -it ubuntu:latest /bin/bash`

#### list all (running) containers

`docker container ls`

#### list all containers

`docker container ls -a`

#### see docker processes

`docker ps`

#### show disk usage of containers

`ps -s`

#### jump into container and use

`docker container exec -it 5bd8a /bin/bash`

#### jump into container and use 

`docker container exec -it 5bd8a /bin/sh`

#### list docker images (class)

`docker image ls`

#### list docker containers (instance)
`docker container ls`

#### stop a running container

`docker container stop 5bd8a090904c`

#### list even stopped containers

`docker container ls -a`

#### remove container
`docker container rm 5bd8a090904c`

#### list even stopped containers

`docker container ls -a`


