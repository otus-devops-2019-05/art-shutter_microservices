# art-shutter_microservices

Repository with home tasks for OTUS/express40 DevOps course

# 21. 27.08 Monitoring-2

side note: if you use two separate docker-compose files to reference single app, make sure you reference network as external in the dependent docker-compose file.

[Docker hub link 346245737637245](https://cloud.docker.com/u/346245737637245/repository/list)

To add docker as data source for Prometheus, you need to enable it in the daemon.json. Read up on this [here](https://docs.docker.com/config/thirdparty/prometheus/).

You can use Telegraf without InfluxDB to export metrics directly into Prometheus, see example [here](https://blog.nobugware.com/post/2016/telegraf_prometheus_metrics_swiss_army_knife/). Use [this image](https://hub.docker.com/_/telegraf) to install Telegraf.

# 20. 22.08 Monitoring-1

Prometheus uses exporters to gather metrics. You can use various exporters depending on the type of task you are performing. Default exporter to gether metrics from a linux host is `node exporter`.

# 19. 13.08 Gitlab CI

Use `.gitlab-ci.yml` file to define your pipelines. Full syntax and explanation as how to use them is [here](https://docs.gitlab.com/ee/ci/yaml/).

You can dockerize runners to improve control over them.

# 17. 06.08 Docker-4

## Networking in docker

When using `host` netwrking, be mindful of the ports allocated on the host machine, as networking system of the container is not isolated in a separate namespace.

When using the default `bridge` networking, mind the internal DNS settings.

If you need to put containers in different networks, you can assign additional networks to containers by running `docker network connect <network> <container>`

## Docker-compose

add a `.env` file to specifay defaults for environment variables in docker-compose.yml.

on setting project base name as environment variable (or in the .env file), [read the docs](https://docs.docker.com/compose/reference/envvars/).

If you use the `docker-compose.override.yml` file, the configs are merged.

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

