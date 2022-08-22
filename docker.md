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

#### see docker running containers

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

#### Docker run say redis detached

`docker run -d redis`

#### To restart a container that has been stopped

```bash
docker ps -a
docker start 83646325276
```

#### bind containers to ports

```bash
docker stop 83646325276
(not runnable )docker run -p[host:container_port] so this would look like
docker run -p6000:6379 -d redis      .... -d detached mode
docker ps    shows binding
```

#### if container is running view logs 

```bash
docker ps
docker logs 83646325276
```

#### name your containers --name

```bash
docker run -d -p6001:6379 --name redis-older redis:4.0
docker ps
```

#### get terminal of running container

```bash
docker exec -it 83646325276 /bin/bash`
or
docker exec -it 83646325276 /bin/sh
```

#### docker run VS docker start

docker run lanches a new container from the image specified

docker start launches an exsisting container that was stoped

`docker start 83646325276`

this will run the container that was set up earlier with docker run and then stopped. note docker start will have all attribs that were created with docker run

EOF

