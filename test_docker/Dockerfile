# indicate base for docker
FROM alpine

# set additional components
# every RUN -> create new layer
RUN apk add npm &&  \
    npm i -g http-server

# add volume
VOLUME /home/server

# set workdir
WORKDIR /home/server

# copy some data to workdir
COPY ./ /home/server/

# promt - for indicate port
EXPOSE 8080

# start container
CMD http-server