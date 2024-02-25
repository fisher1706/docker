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

# run command in container -> [exec] -> [pg] - name of container -> [bash] - command
```shell
docker exec -it pg bash
```

# command for start container has number "1" - is "1" stop -> exit from container 

# attach to docker process [stupefied_hopper] - name of container -> can be not active
```shell
docker attach stupefied_hopper
```

# start postgres with open port -> port local - first
```shell
docker run --name pg -e POSTGRES_PASSWORD=123 -d -p 5433:5433 postgres
```