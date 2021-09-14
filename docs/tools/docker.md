# Docker

Command | Description
---------|----------
`docker run` | Runs an image in docker
`docker ps` | Shows running containers
`docker ps -a` | Shows all including previously stopped containers
`docker stop` | Stops container
`docker rm` | Removes a container
`docker images` | List images
`docker rmi` | Removes image
`docker pull` | Pulls image from registry
`docker exec` | Execute a command on a running container
`docker run -it [container] bash` | Run container in interactive mode
`docker build -t [image name] -f dockerfile .` | Builds a docker image

By default docker does not listen to standard input
Use the -I parameter to map the docker standard input to host standard input for interactive mode
Use the -t to attach to the terminal

Every docker container is assigned an internal ip address accessible from the docker host
You can also access using the docker host ip address, but need to map a free port on the host to the application port on the container
