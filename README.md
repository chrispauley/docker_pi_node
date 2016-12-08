# Project docker_pi_node

## Description
This is a base setup for a Docker image for an ARM implementation which includes a specific build for Node. This is intended to run on a Raspberry Pi.

## Setup
You need a Raspberry Pi installed and assessable via ssh.
Install Docker on your Raspberry Pi. Here's a [helpful guide](https://www.raspberrypi.org/blog/docker-comes-to-raspberry-pi/).
tl;dr
Login into your Raspberry Pi and use the Jessie image:
````
curl -sSL https://get.docker.com | sh
````

If you want to use this github project to create your own image:
````
git clone https://github.com/chrispauley/docker_pi_node.git my_project
````
Then modify the docker file and build a new image to your specifications. If you want to use this image as-is, then can login to your raspberry pi that has docker and pull it from [hub.docker.com](https://hub.docker.com/r/chrispauley/node/).
````
#To pull that image as is then login to your raspberry pi
ssh pi@192.168.0.62
docker pull chrispauley/node:arm
sudo docker run --name=arm_node -it chrispauley/node:arm

# This puts you into the Node REPL environment.
# in another terminal window that's connected to your pi
pi@raspberrypi:~ $ docker ps
CONTAINER ID        IMAGE                  COMMAND                  CREATED             STATUS              PORTS               NAMES
ff51e9a879b7        chrispauley/node:arm   "/usr/bin/entry.sh no"   3 minutes ago       Up 3 minutes  
````

That confirms that you're running. 
