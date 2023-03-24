# spring-boot-zuul-eureka
A template for spring cloud projects containing the eureka (service discovery) and zuul (load balancer and reverse proxy)
=======

## Prerequisite

- OpenJDK 11
- Docker and docker-compose

## Build images

- run `sh create-all-image.sh`

## Quick launch

- `sh launch-stack.sh`, it will launch the stack with 4 instances of hello-service
- Wait a little, zuul need to synchronize services with eureka (about 1 or 2 minutes)
- Go to `http://localhost:8080/rest/hello-service/**` to access the hello service
- Go to `http://localhost:8080/rest/post-service/**` to access the post service

## Launch the stack

- Make sure you have port 8761 and 8080 open and free
- `docker-compose up` optionally you can add `-d` option for detached mode.
- Wait launching
- Go to `http://localhost:8761` to see eureka interface
- Wait a little, zuul need to synchronize services with eureka (about 1 or 2 minutes)
- Go to `http://localhost:8080/rest/hello-service/**` to access the hello service
- Go to `http://localhost:8080/rest/post-service/**` to access the post service
- To improve service instance : `docker-compose scale hello-service=4`

**You can see on `http://localhost:8080/rest/hello-service/api/hello` different ip address thank to the load balancing.**

**To stop all container `docker-compose down`**
