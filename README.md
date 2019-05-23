# container management

* docker images
* docker ps
* docker pull
* docker push
* docker run
* docker inspect
* docker exec

## Running first container

```shell
docker pull ubuntu:latest

docker run -it ubuntu:latest /bin/bash
```

## Using volumes

* mkdir ~/html
* echo 'plop' > ~/html/index.html

```shell
docker pull nginx:latest

docker run --name some-nginx -v `pwd`:/usr/share/nginx/html:ro -d nginx
```

* How can I get static content?
  * docker inspect

## Port forwarding

```shell
docker pull nginx:latest

docker run --name some-nginx -v `pwd`:/usr/share/nginx/html:ro -p 8080: 80 -d nginx
```

## Build own nginx

* create Dockerfile

```shell
docker build -t my-nginx:my-tag .
```