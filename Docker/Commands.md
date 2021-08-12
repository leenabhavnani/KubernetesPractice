#### docker commands in order

    docker info
    docker version
    docker images
    docker ps
    docker ps -a
    
    docker pull redis
    docker run -d redis
    docker container run --publish 80:80 -d nginx

    docker container ls
    docker container stop
    docker container ls -a
    docker container logs <container_id>
    docker container top <container_id>
    docker container rm <container_id>
    docker container stats
    docker container inspect <container_id>
    docker container exec -it <container_id> bash

    docker images
    docker image inspect <image_id>
    docker image pull mongo
    docker image ls
    docker history nginx

    docker run -d -p 80:80 my-nginx:1.0
    curl localhost:80  
    
    docker build -t leenabhavnani/my-nginx:1.0 .     

    docker login
    docker push leenabhavnani/my-nginx:1.0
