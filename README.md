# art-shutter_microservices

Repository with home tasks for OTUS/express40 DevOps course

# 16. 01.08 Docker-3

During builds, docker uses cache if the result of the command is similar to the result in cache AND if the layers above the target are not uinque.

To build smaller images, use Alpine linux. Don't forget to clean package manager's cache if it's enabled. 

To make layers thinner, combine RUN commands into one layer.

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

running docker:
- `docker diff <image>`
- `docker stop`
- `docker kill`
- `docker start`
- `docker restart`
- `docker run --nme <name> --rm -it <image:tag> command`

Work log:
- learned docker commands
- deployed docker'd app to new GCP project 

