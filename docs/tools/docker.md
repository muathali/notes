# Docker

## Container Commands

Command | Description
---------|----------
`docker container run` | Runs an image in docker (new way)
`docker container run --publish  80:80 --detach nginx` | Detached ..
`docker container ls` | List running containers
`docker container stop <container Id>` | stops a running container
`docker container logs <container Id>` | print logs from container
`docker container inspect` | Get information about the container
`docker container stats` | Live stats about the container
`docker exec` | Execute a command on a running container
`docker run -it [container] bash` | Run container in interactive mode
`docker container port <container id>` | show port mapping

## Other Commands

Command | Description
---------|----------
`docker version` | Version information
`docker info` | Docker information
`docker ps` | Shows running containers
`docker ps -a` | Shows all including previously stopped containers
`docker stop` | Stops container
`docker rm` | Removes a container
`docker images` | List images
`docker rmi` | Removes image
`docker pull` | Pulls image from registry
`docker build -t [image name] -f dockerfile .` | Builds a docker image
`docker ps --filter status=exited -q | xargs docker rm` | remove all stopped containers

By default docker does not listen to standard input
Use the -I parameter to map the docker standard input to host standard input for interactive mode
Use the -t to attach to the terminal

Every docker container is assigned an internal ip address accessible from the docker host
You can also access using the docker host ip address, but need to map a free port on the host to the application port on the container
