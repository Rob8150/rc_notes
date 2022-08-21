## Docker Notes
### run docker as non root

#### https://docs.docker.com/engine/install/linux-postinstall/

### example

 sudo apt-get install docker.io
 sudo docker --version
 sudo docker info
 docker image ls
 sudo docker image ls
 docker image pull ubuntu:latest
 sudo docker image pull ubuntu:latest
 sudo docker images
 sudo docker container run -it ubuntu:latest /bin/bash
 sudo docker container ls
 sudo docker container exec -it 5bd8a /bin/bash
 sudo docker image ls
 sudo docker container ls
 sudo docker container stop 5bd8a090904c
 sudo docker container ls -a
 sudo docker container rm 5bd8a090904c
 sudo docker container ls -a

