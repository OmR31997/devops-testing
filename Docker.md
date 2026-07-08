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

Common Commands:
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

Docker is an open-source platform designed to automate the deployment, scaling, and management of applications using containerization technology. It allows developers to package applications with all their dependencies into standardized units called containers that run consistently across different computing environments.

## Why we use Docker?

To resolve Security, Resource Allocation, and App Dependencies

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

## Volume -

A volume is a persistent storage mechanism managed by Docker that exists outside of the container's writable layer. Volumes allow data to be shared between containers and persist independently of container lifecycle.

## Dockerfile

- A Dockerfile is a simple plain text file that take the code and the defined all the depedencies.
- A Dockerfile is a text file that contains instruction to build docker image.
- The instruction defined the environment inside the container including what s/w to install, what files to copy, & what commands to run.

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

- docker ps
  Description: This will display the output of running container.

- docker ps -a
  Description: This will display the output of container that are running as well as stop all the containers.

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

# Dockerfile Instructons

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

Note:
exec - Execute a command in a running container
i - interactive mode (-i)
t - terminal (-t)
d - runs the container in detached mode (background). Without -d, the container would run in the foreground and block your terminal.
--name mywebapp → assigns a custom name (mywebapp) to the container

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

Step-6: npm install (Install dependencies)
Step-7: docker build --no-cache -t node-app . (Build the Docker image)
Step-8: docker run -d -p 3000:3000 node-app (Run the container)
Step-9: docker ps (Verify the container is running)
