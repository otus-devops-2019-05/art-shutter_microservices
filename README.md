# art-shutter_microservices

Repository with home tasks for OTUS/express40 DevOps course

# 15. 30.07 Docker-2

## Useful docker commands:

images:
- `docker images (image ls)`
- `docker rmi`
- `docker build -t image:tag /path/to/Dockerfile`

containers:
- `docker inspect`
- `docker ps`
- `docker ps -a`

docker-in-docker:
- `docker run --privileged --cap-add=NET_ADMIN`

docker registry:
- `docker login`
- `docker push image:tag`
you need to retag your image to show 

