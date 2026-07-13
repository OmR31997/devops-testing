# Basi Urls

https://docs.docker.com/get-started/
https://docs.docker.com/get-started/docker-overview/
https://docs.docker.com/get-started/introduction/
https://docs.docker.com/get-started/docker-concepts/the-basics/what-is-a-container/
https://www.docker.com/play-with-docker/
https://labs.play-with-docker.com/

All dependencies with Docker
sudo apt install docker.io

Usage: docker [OPTIONS] COMMAND

A self-sufficient runtime for containers

# Common Commands:

run Create and run a new container from an image
exec Execute a command in a running container
ps List containers
build Build an image from a Dockerfile
bake Build from a file
pull Download an image from a registry
push Upload an image to a registry
images List images
login Authenticate to a registry
logout Log out from a registry
search Search Docker Hub for images
version Show the Docker version information
info Display system-wide information

Management Commands:
agent* Docker AI Agent Runner
ai* Docker AI Agent - Ask Gordon
builder Manage builds
buildx* Docker Buildx
compose* Docker Compose
container Manage containers
context Manage contexts
debug* Get a shell into any image or container
desktop* Docker Desktop commands
dhi* CLI for managing Docker Hardened Images
extension* Manages Docker extensions
image Manage images
init* Creates Docker-related starter files for your project
manifest Manage Docker image manifests and manifest lists
mcp* Docker MCP Plugin
model* Docker Model Runner
network Manage networks
offload* Docker Offload
pass* Docker Pass Secrets Manager Plugin (beta)
plugin Manage plugins
sandbox* Docker Sandbox
sbom* View the packaged-based Software Bill Of Materials (SBOM) for an image
scout* Docker Scout
system Manage Docker
volume Manage volumes

Swarm Commands:
swarm Manage Swarm

Commands:
attach Attach local standard input, output, and error streams to a running container
commit Create a new image from a container's changes
cp Copy files/folders between a container and the local filesystem
create Create a new container
diff Inspect changes to files or directories on a container's filesystem
events Get real time events from the server
export Export a container's filesystem as a tar archive
history Show the history of an image
import Import the contents from a tarball to create a filesystem image
inspect Return low-level information on Docker objects
kill Kill one or more running containers
load Load an image from a tar archive or STDIN
logs Fetch the logs of a container
pause Pause all processes within one or more containers
port List port mappings or a specific mapping for the container
rename Rename a container
restart Restart one or more containers
rm Remove one or more containers
rmi Remove one or more images
save Save one or more images to a tar archive (streamed to STDOUT by default)
start Start one or more stopped containers
stats Display a live stream of container(s) resource usage statistics
stop Stop one or more running containers
tag Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE
top Display the running processes of a container
unpause Unpause all processes within one or more containers
update Update configuration of one or more containers
wait Block until one or more containers stop, then print their exit codes

Global Options:
--config string Location of client config files (default
"C:\\Users\\omr31\\.docker")
-c, --context string Name of the context to use to connect to the
daemon (overrides DOCKER_HOST env var and
default context set with "docker context use")
-D, --debug Enable debug mode
-H, --host string Daemon socket to connect to
-l, --log-level string Set the logging level ("debug", "info",
"warn", "error", "fatal") (default "info")
--tls Use TLS; implied by --tlsverify
--tlscacert string Trust certs signed only by this CA (default
"C:\\Users\\omr31\\.docker\\ca.pem")
--tlscert string Path to TLS certificate file (default
"C:\\Users\\omr31\\.docker\\cert.pem")
--tlskey string Path to TLS key file (default
"C:\\Users\\omr31\\.docker\\key.pem")
--tlsverify Use TLS and verify the remote
-v, --version Print version information and quit

Run 'docker COMMAND --help' for more information on a command.

For more help on how to use Docker, head to https://docs.docker.com/go/guides/

## What is Docker?

- Docker is an open-source platform designed to automate the deployment, scaling, and management of applications using containerization technology. It allows developers to package applications with all their dependencies into standardized units called containers that run consistently across different computing environments.

- Docker is tool that helps in developing, building, and deploying executing software in isolation. It does so by creating containers that completely wrap a software.

## Why we use Docker?

- To resolve Security, Resource Allocation, and App Dependencies

- Simple, fast, Easycollaboration, Build for developer, by developers, Docker community

## Docker Syntax (run, pull, images, push, etc)

docker run

## Container - Code + Dependencies

- A container is an OS process, that behaves like a virtual machine (VM) using the concept of NAMESPACES and CGROUP.
  A container is a lightweight, standalone, executable package that includes everything needed to run a piece of software: code, runtime, system tools, libraries, and settings.

## Types of Container

- Docker <- Docker INC
- CRI-O
- ContainerD
- RKT(Roket)

## Image -

An image is a static specification from which containers are created. It contains the application code, runtime, libraries, environment variables, and configuration files needed to run the container.

## Registry -

A registry is a storage and content delivery system that holds named Docker images, available for use by Docker clients. Docker Hub is the default public registry where users can find and share images.

A store for images. such as Docker Hub or private registry. we push and pull images here.

## Volume -

A volume is a persistent storage mechanism managed by Docker that exists outside of the container's writable layer. Volumes allow data to be shared between containers and persist independently of container lifecycle.

## Dockerfile

- A Dockerfile is a simple plain text file that take the code and the defined all the depedencies.
- A Dockerfile is a text file that contains instruction to build docker image.
- A plain-text recipe of instuctions that tells how to build an images.
- The instruction defined the environment inside the container including what s/w to install, what files to copy, & what commands to run.

## Docker Compose

- A tool to define and run multi-container applications from one YAML file.

## Docker Engine

- The backend service (daemon) that builds images and runs container on a host.

^
From the Dockerfile we build docker image.

^
From the image we create container

PS C:\Users\omr31> docker run -d --name mywebapp nginx
Unable to find image 'nginx:latest' locally
latest: Pulling from library/nginx
1645c1e06f46: Pull complete
df68ee7e7a00: Pull complete
cd9307c9ecd8: Pull complete
acf093e7a04f: Pull complete
fcb6fd84b2a0: Pull complete
e95a6c7ea7d4: Pull complete
1b30016634d5: Pull complete
1cf7d051b485: Download complete
e2c07e54e55a: Download complete
Digest: sha256:ec4ed8b5299e5e90694af7750eb6dffd2627317d30544d056b0371f8082f7bce
Status: Downloaded newer image for nginx:latest
fb68c8588e4db623cf3130c08a54be0924ff6f6c069d4611c4cbd7708bfa5005
PS C:\Users\omr31> docker ps
CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES
fb68c8588e4d nginx "/docker-entrypoint.…" 10 seconds ago Up 7 seconds 80/tcp mywebapp

## Launch a Container

#1: We have launched container using NGINX Image
docker run <h_verb_name>

^
#2 We see that container is running
docker ps

^
#3 We list down all the NGINX process
ps aux

^
#4 We list specific process
ps aux |grep -i nginx

^
#5 We stop the container
docker stop mywebapp

^
#6 We killed NGINX master process - that killed all the NGINX child process
kill -9 620 (-9 means forcefully)

^
When we killed the process, container also got killed.

^
Container are NOTHING but OS process.

^
If it is an OS process, how it can run my CODE within it

## How Linux Works?

| Process | System Call | Kernel | H/W, RAM/CPU/HDD | User Space |
| ------- | ----------- | ------ | ---------------- | ---------- |

Note: Each process will generate own system call. Every process will have its own system call. System call interact with kernel there have only one kernel. That kernel will allocate h/w.

The user space is where the application code runs, while the kernel manages the hardware resources. When a process makes a system call, it requests the kernel to perform operations like reading from disk, writing to network, or allocating memory. The kernel then executes these operations on behalf of the process and returns the results. This separation ensures that applications run in a protected environment without direct access to hardware, providing security and stability.

In the context of Docker, when you run a container, you are essentially creating a new process (or set of processes) in user space that executes your application code. The container shares the host's kernel but has its own isolated user space, filesystem, and network namespace.

## NAMESPACES (What we can see)

NAMESPACES are feature of the linux kerrnel that partition kernel resources such that one set of process sees one set of resources, while another set of processes sees a different set of resources. The feature works by having the same namespaces for a set of processes, creating isolated environments for each namespace.

## CGROUPS (How much we can see)

It is abbriviated from Control group is Linux kernel feature that limits, accounts for, and isolates the resource usage(CPU, memory, disk I/O, etc) of a collection of processes

## Docker Architecture

1: Docker CLI
2: Docker Deamon
3: Docker Hub

DOCKER_CLI => DORCKER_DEAMON => DOCKER_HUB

#1: Docker CLI
The place where we run all the docker commands.

#2: Docker Deamon
Deamon is the main process. Most of the time CLI and Daemon work on the same machine.

#3: Docker Hub
Docker Hub is a cloud-based repository service where developers and teams can push (upload) and pull (download) Docker container images anytime via the internet.

Note: When we type anything at the CLI, that command get converted into an API request and it's go to DockerD. Whatever we mentioned in the commanad, docker D will do all the heavy lifting.

## Docker Commands

- docker -v or docker --version
  Description: This will display the Docker version information.

- docker info
  Description: This will display system-wide information about Docker.

- docker ps
  Description: This will display the output of running container.

- docker pull <image_name>
  Description: This will download the specified image from Docker Hub (registry) to the local machine.

- docker images
  Description: This will display list of all images.

- docker run <image_name>
  Description: This will pull that image, create container as well as run it.

- docker image inspect <image_name>
  Description: This will display detailed information about the specified image.

- docker history <image_name>
  Description: This will show the history of an image including all the layers and commands used to build it.

- docker ps -a
  Description: This will display the output of container that are running as well as stop all the containers.

- docker tag <image_name> new: tag
  Description: Add a new tag/name to an exiting image.

- docker stop <container_id>
  Description: This will stop a running container by sending it a SIGTERM signal.

- docker start <container_id>
  Description: This will start a stopped container.

- docker restart <container_id>
  Description: This will restart a running container.

- docker rm <container_id>
  Description: This will remove a stopped container.
  Description: This will remove a stopped container.

- docker rm -f <container_id>
  Description: This will forcefully remove a running container.

- docker rmi <image_name_or_id>
  Description: This will remove the specified image.

- docker container prune
  Description: This will remove all stop containers.

- docker image prune
  Description: This will remove all unused images.

- docker run -d --name newwebapp nginx
  Description: This will run a new container named 'newwebapp' in detached mode using the NGINX image.

- docker run --dit --name myalpine alpine ash
  Description: This will run a new container named 'myalpine' in detached mode using the Alpine image and start the 'ash' shell.

- docker exec -it <container_id> bash
  Description: This will execute the 'bash' command inside the running container with interactive terminal support.
  and to go outside of container Ctr + p + q

- df -h
  Description: Through this display file system of container. Display disk space usage in human-readable format.

- docker attach <container_name_or_id>
  Description: This will attach your terminal to a running container, allowing you to interact with it directly.

# Alpine

Alpine is a linux image specially designed for container. It is very light version of container.

# Dockerfile Basic Instructons

FROM - This command specifies the base image to use for the docker image being built
FROM ununtu:20.04

RUN - This command executes commands within the Docker image during the build process.
RUN apt-get update && apt-get install -y nginx

COPY - This command copies files from the host machine to the Docker image.
ADD - This command copy files and directories from the host machine into the Docker image.

Note: COPY is faster than ADD, and ADD has additional features like extracting tar archives. Copy the content from our base machine inside the container.

WORKDIR - This command set the working directory for subsequent instruction in the Dockerfile.
WORKDIR /app

EXPOSE - This command specifies the ports that the container will listen on at run time.
EXPOSE 80

CMD - This command sets the default command to run when the container starts.

CMD or ENRYPOINT - This commands specifies the ports that the container will listen on at runtime.
CMD ["nginx", "-g", "daemon off;"]

ENV - This command sets environment variables inside the container.

USER - This command sets the user to run the container as.

exec - Execute a command in a running container

## Common "Docker run" flags

-d: Runs the container in detached mode (background) and print the containerId. Without -d, the container would run in the foreground and block your terminal.

-p: host: container: (port mapping) → Map a port on your host machine to a port inside the container (-p).

--name <name>: Assigns a custom name (mywebapp) to the container

-e KEY=value: Set an environment variable inside the container.

-v volume:path: Mount a volume or bind mount for persistent data.

--rm: Automatically remove the container when it exists.

- i: interactive mode (-i)

- t: terminal (-t)

-it: Interactive + TTY -- Attach a terminal for shell.

--network <net>: Connect the container to a specific network.

-- restart <policy>: Auto-restart policy (e.g., Always, unless stopped).

## Run nginx in the background, named web', port 8080 -> 80

docker run -d --name <imageName> -p <hostPort>: <containerPort> nginx

## Run an interactive ubuntu shell that self-deletes on exit

docker run -it --rm ubuntu bash

First 3000 → host port (your local machine).
Second 3000 → container port (inside Docker).
This means: requests to http://localhost:3000 on your machine are forwarded to port 3000 inside the container.

Shell Commands
pwd - print working directory
ls - list directory contents
cd - change directory
cat - concatenate and display files
echo - display a line of text
mkdir - make directories
rm - remove files or directories
touch - create empty file or update timestamp

## To Exlore location

explorer "\\wsl$\docker-desktop\root"

## Code With Docker

🖋️ Basic vi commands
Enter insert mode (to type/edit) → press i

Exit insert mode → press Esc

Save and quit → type :wq then press Enter

Quit without saving → type :q! then press Enter

Save only (stay in editor) → type :w then press Enter

So in your case:

Press Esc (to make sure you’re not in typing mode).

Type :wq and hit Enter.
→ That will save your changes to app.js and exit back to PowerShell/Git Bash.

⚡ But since you’re on Windows
If you don’t want to deal with vi at all, you can use:

notepad app.js

code app.js (if VS Code is installed and PATH is set)

That way you edit files in a familiar GUI editor instead of the terminal-based vi.

Step-1: mkdir <DirectoryName>
Step-2: cd <DirectoryName>
Step-3: vi app.js (Write nodejs based code)
Step-4: vi package.json () (Create package.json file with dependencies and scripts)
Step-5: vi Dockerfile (Create Dockerfile with instructions)
Ex:
FROM node: 26-alpine3.23 (visit: https://hub.docker.com/_/node)
FROM node:22-alpine AS builder

WORKDIR /app

COPY package\*.json ./

RUN npm install

COPY . .

EXPOSE 9000

RUN npm run build

CMD ["node", "dist/main"]

Step-7: docker build --no-cache -t node-app . or docker build -t my-nestjs-app . (Build the Docker image with node.js case)
Step-8: docker run -d -p 3000:3000 node-app (Run the container)
Step-9: docker ps (Verify the container is running)

## Docker Volume

- A Volume is persistent storage mechanism managed by Docker that exited outside of the container's writable layer. Volume allow yoy to shared data between containers and persitent independently (Even if the container dies volumer still alive (Data survives)) outside of the container lifecycle.

- A volume is a storage box outside the container.

- Docker Volumes involve several Docker concepts together, so if you don't understand the basics first, the practices feel like memorizing commands.

## Volume Commands

- docker volume create nginx-data
  Description: Creates a new volume named nginx-data outside of container.

- docker volume ls
  Description: Lists all existing Docker volumes

- docker volume inspect nginx-data
  Description: Displays detailed information about the nginx-data volume
  Example:
  [
  {
  "Mountpoint":
  "/var/lib/docker/volumes/nginx-data/_data"
  }
  ]
  Meaning
  Docker stores volume somewhere on disk.
  You usually don't edit it directly.

- docker volume rm nginx-data
  Description: Removes the nginx-data volume

- docker run -v nginx-data:/usr/share/nginx/html nginx
  Description: Runs an NGINX container using the nginx-data volume to persist HTML content

## Docker & Debugging Containers

- docker logs <container_id>
  Description: This will display container's logs (Add -f to follow live).

- docker exec -it <container_id> bash
  Description: Open a shell inside a running container.

- docker inspect <container_id>
  Descritpion: This will display full low-level JSON details.

- docker stats
  Description: This will display Live CPU, memory, and I/O usage of containers.

- docker top <container_id>
  Description: Show the process running inside a container.

- docker port <container_id>
  Description: Show the container's published port mappings.

- docker cp <container_id>: /path ./local
  Description: : Copy files between container and host.

- docker diff <container_id>
  Description: Show files changed in the writable layer.

## System, Cleanup & Info

- docker system df
  Description: Show disk usage by images, containers, and volume.

- docker system prune
  Description: Remove unused data (stopped containers dangling images network)

- docker system prune -a --volume
  Description: Aggresive cleanup, including unused images & volumes.

- docker login / logout
  Description: Authenticate to a registry to push/pull private imagess.

- docker push <image>
  Description: Upload a tagged image to a registry.

- docker search <term>
  Description: Search Docker Hub for images.

Note: docker system prune -a --volumes is powerful and irreversible - it can delete images you would have to download again and volumes containing real data. Read what it list before confirming. especially on shared or production mode.

## The Anatomy of a Dockerfile

Each line a Dockefile is an instruction in the from instruction argument. Instructions are executed in order, and most of them create a new image layer. here are the instructions we will use everyday.

- FROM
  Set the base image to build on (e.g., node:26.0). Always the first instruction.

- WORKDIR
  Description: Set the working directory for the instruction that follow; it if need.

- COPY
  Description: Copy files/folders from the build context into the image.

- ADD
  Description: Like COPY, but can also fetch URLs and auto-extract tar archieve (prefer COPY).

- RUN
  Description: Executes a command at build time (e.g. installing packages) and commits the result as a layer.

- ENV
  Description: Set an enviroment variable that persists in the image and running containers.

- ARG
  Description: Defines a build-time variable passed with --build-arg (not present at runtime).

- EXPOSE
  Description: Documents which port the application listens on (Does not actully publish it).

- CMD
  Description: The default command run when the container starts; easily overridden at run time.

- ENTRYPOINT
  Description: The fixed executable for the container; CMD becomes its default arguments.

- VOLUME
  Description: Declares a mount point for external, persistent storage.

- USER
  Description: Set the user that subsequent instruction and the container run as (use a non-root-user)

## Docker Volume

- docker volume create <volumeName>
  Description: To create volume in docker.

- docker run -d --name db \ -v <volumeName>:/var/lib/<directoryName>/data \ <image>

Note: The database survives even if the container is deleted and recreated.

## Docker Environment

# Docker Engine

Docker engine is as the name suggest, its technology that allows for the creation and managemnent of all the Docker Processes. It has three major parts to it.

- Docker CLI
- Docker API
- Docker Daemon

# Docker Object

- Docker Images
  Description: Docker images are sets of instructions that are used to create containers and execute code inside it.

- Docker Containers
  Description:
- Docker Volumes
- Docker Networks
- Docker Swarm Nodes & Service

# Docker Registry

# Docker Compose

# Docker Swarm
