#### docker commands in order

    docker version
    docker images
    docker pull redis
    docker run -d redis
    docker ps
    docker ps -a


    docker build -t my-nginx:1.0 .
    docker run -d -p 80:80 my-nginx:1.0
    curl localhost:80

    docker login
    docker push leenabhavnani/my-nginx:1.0
