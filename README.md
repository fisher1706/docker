# https://www.youtube.com/watch?v=I18TNwZ2Nqg

# docker command

# to see all images "OR"
```shell
    docker images && docker images -a
```

# to start "hell-world"
```shell
    docker run hello-world
```

# to search "tomcat"
```shell
    docker search tomcat
```

# to pull "tomcat"
```shell
    docker pull tomcat
```

# to see running containers
```shell
    docker ps
```

# to see all containers
```shell
    docker ps -a
```

# to run "nginx" [interactive] with connect by ports -> to see result: localhost:8080
```shell
    docker run -it -p 8080:80 nginx
```

# to run "ubuntu" [interactive] with command "ps -A" -> work only when command work
```shell
    docker run -it ubuntu ps -A
```

# to run "nginx" [daemon] with connect by ports -> to see result: localhost:8080
```shell
    docker run -d -p 8080:8080 nginx
```

# to delete image "hello-world"
```shell
    docker rmi hello-world
```

# to remove container "hello-world"
```shell
    docker rm hello-world
```

# to build image "test:v1" from Dockerfile
```shell
    docker build -t test:v1 .
```

# to copy "test:v1" to "test:copy"
```shell
    docker tag test:v1 test:copy
```

# to connect to container "fc76530520af - nginx [must be]"
```shell
    docker exec -it fc76530520af /bin/bush
```

# to create image from container "1872f3fe6615 [must be and must run]"
```shell
    docker commit 1872f3fe6615 zapel:v2
```


# https://www.youtube.com/watch?v=Sa7uOGczoHc&list=PLU2ftbIeotGoGFC_2lj-OplT_cItXfu48&index=1
# -------------------------------------------Set Run Docker Without Sudo------------------------------------------------

# create group "docker"
```shell
sudo groupadd docker
```

# add user to group "docker"
```shell
sudo usermod -aG docker $USER
```

# update changes in groups
```shell
newgrp docker
```
# ----------------------------------------------------------------------------------------------------------------------

# docker + [Tab] -> to see all docker commands

# delete all container
```shell
docker rm $(docker ps -aq)
```

# delete all image
```shell
docker rmi $(docker images -q)
```

# pull and run alpine -> it[interactive] -> sh[command] (shell)
```shell
docker run -it alpine sh
```

# start container -> [sleepy_raman] - name of container
```shell
docker start sleepy_raman
```

# to exit from container -> run in container
```shell
exit
```

# stop container -> [sleepy_raman] - name of container
```shell
docker stop sleepy_raman
```

# pull image [postgres:10.8]
```shell
docker pull postgres:10.8
```

# postgres -> [-d] - daemon -> [--name] -> name for db -> [e] - password : from documentation
```shell
docker run --name pg -e POSTGRES_PASSWORD=postgres -d postgres
```

# run command in container from command line -> [exec] -> [pg] - name of container -> [bash] - command
```shell
docker exec -it pg bash
```

# command for start container has number "1" - is "1" stop -> exit from container 

# attach to docker process [sleepy_visvesvaraya] - name of running container
```shell
docker attach sleepy_visvesvaraya
```

# exit from process of container without "stop" container
# [Ctrl] + [P] next [Ctrl] + [Q]


# start postgres with open [port] -> port local - first
```shell
docker run -d --name pg -e POSTGRES_PASSWORD=123 -p 5432:5432 postgres
```

# connect to postgres by command line -> "in local pc -> connect to pgAdmin -> work write now - password: [qwerty]"
```shell
sudo -u postgres psql -h localhost
```

# attach volume to container -> "-v [local path]:[container path]"
```shell
docker run -it -v /home/fisher:/home/new_fisher alpine
```

# ------------------------------------------------create images---------------------------------------------------------

# 1. download container -> set nme for container [node-dru]
```shell
docker run -it --name node-dru alpine sh
```

# 2. add nodejs in container -> work in container
```shell
apk add nodejs
```

# 3. check nodejs
```shell
node --version
```

# 4. exit from container
```shell
exit
```
# 5. create image -> format: [name of container] [name of account on dockerhub]/[name of repository]:[version]
#                    [node-dru] - name of container
#                    [fzapel] - name of account on docker hub
#                    [node-dru] - name of repository
#                    [v20.1] - version
```shell
docker commit node-dru fzapel/node-dru:v20.1
```

# 6. login to dockerhub -> user_name[fzapel], password[zapel1706]
```shell
docker login
```

# 7. push image to dockerhub
```shell
docker push fzapel/node-dru:v20.1
```

# -------------------------------------------DOCKERFILE-----------------------------------------------------------------

# create image from Dockerfile -> [-t] - tag for image -> [.] - take Dockerfile from current dir
```shell
cd test_docker && docker build -t fzapel/node:v1 .
```

# start container -> according to current Dockerfile -> folder "test_docker" can see on http://127.0.0.1:3000/
```shell
docker run -it --name node-dru -p 3000:8080 fzapel/node:v1
```

# push image on dockerhub
```shell
docker push fzapel/node:v1
```

# 1. Dockerfile with [git]
```shell
docker build -t fzapel/test_internal:v1 -f Dockerfile.git .
```

# -------------------------------------------docker compose-------------------------------------------------------------

# create image -> to find [dockerfile] in dir [docker_compose]
```shell
docker build -t fisher-php ./docker_compose
```

# check image -> must have image [fisher-php]
```shell
docker images
```

# start container [fisher-php] with name [zapel]
```shell
docker run --name zapel -p 8000:80 -d fisher-php
```

# to see started containers
```shell
docker info
```

# start docker-compose [postgres]
```shell
cd docker_compose && docker-compose build && docker-compose up
```

# localhost:8080 -> phpMyAdmin -> [user] - root -> [password] - 12345

# start docker-compose [mysql]
```shell
docker-compose build && docker-compose up
```

# localhost:8080 -> phpMyAdmin -> [user] - root -> [password] - 12345

# stop containers [Ctrl] + [C]
