[[Home-Sparta]]
# Micro-services
#docker
- Refactoring monolith architecture into smaller chunks

## Agenda
- Micro-services Architecture
- Docker
- Kubernetes (K8)

## Docker:
[Arch install](https://wiki.archlinux.org/title/Docker)
Commands exctracted from the link above.
- `pacman -S docker`
- `sudo systemctl enable docker.service`
	- The start and status to confirm it's working 
- `docker info` 
	- Should output a permission error
	- resolved by `sudo`
- To verify that it works use the *Hello world* package
	-  `docker run -it --rm archlinux bash -c "echo hello world"`
		- *Note* need to use sudo and also the `--privileged` argument 

### Login
To link account and terminal use the script bellow:
`sudo docker login`

## Packages
*find* a package from the [docker hub website](https://hub.docker.com/) and run `sudo docker pull` so that it is downloaded and stored on the local machine.
to launch the container, run `sudo docker run <container>`

#### Images
`docker images`
removing 
`docker rmi <image-name>`

## Copying into the docker image directory 
`sudo docker cp <local/file> <docker ps instance>:<pick/a/location/with/name.html`

## Commit
`docker commit <docker ps instance name> <user-name>/<repo-name>[:tags]`
*Hint*: tags can be left empty to become the place holder *:latest*
## Push
After you have finished with the commit, a push can be done
`docker push <username>/<repo-name>[:tags]`
tags like always can be left empty 

### Detached
using the package *ghost* to run in a detached way use the `-d` argument.
`docker run -d -p 2368:2368 ghost`
- We have defined the __ports__ found on the docker hub website.
## Port
`-p <local port>:<docker port>`
### Listing
- `docker ps` and `docker ps -a`
This will show all active containers

### Container interaction
`docker exec -it <container id from docker ps> bash`
This will allow us to explore the contents of the container.

Competitors
- Cryo
