# https://www.youtube.com/watch?v=I18TNwZ2Nqg


# docker command

# to see all images 
```shell
    docker images
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

# to run "nginx" [daemon] with connect by ports -> to see result: localhost:8080
```shell
    docker run -d -p 8080:8080 nginx
```

# to delete image "hello-world"
```shell
    docker rmi hello-world
```

# to remove image "hello-world"
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