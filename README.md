# Workshop 2

In this workshop we'll get started with containers using docker.

## Pre-requisites

You will need to have installed Docker Desktop :
https://www.docker.com/products/docker-desktop/

## Hello World

To check docker is working, run a Hello World container.

```
docker run hello-world
```

## Pull a container image and run it

First, we'll run a pre-built container image that contains an nginx webserver.

```
docker run --name my-nginx -d -P nginx
```

To get some info about running containers, try 
```
docker ps
```

You should be able to figure out which host port is mapped to the container port 80, and point a browser at it.

## Build a container using a dockerfile

This tutorial repo includes information to build two containers, 'nginx-static' and 'python-prog'.  Build the ngingx example using :
```
cd nginx-static
docker image build -t nginx-static .
```

Look at `nginx-static/dockerfile`. This simple example builds a container based on `nginx`, adding an HTML file and an image to create a static website.

Now run the container :
```
docker run --name nginx-static-1 -P -d nginx-static
```

As before, you should be able to point a web browser at the container and view the website.

## Build all containers using compopse

Have a look in the file 'docker-compose.yml'.  

Buid and run all the containers using :
```
docker compose up
```
