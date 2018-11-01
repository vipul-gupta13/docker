## What is Docker?
Docker is a software bucket comprising everything necessary to run the software independently. It is one of the containerization software, that helps you create containers for your micro-services.

### Lets start.
I hope, by now you must have got an idea of containers and why are they necessary.
To get started with docker, keep the following things in mind :

- Docker have two major components :
  - Image 
  - Container

**Image** : A docker image is like snapshot of OS'es with all the required softwares and configuration pre-installed in it. Simply put, you can say, I can install all the requisites, dependencies and my own code to a machine and then take snapshot of that state, that can be easily distributed and re-used. That snapshot is called image.

**Container** : As the name suggest, container works as the outer shell(in literal terms) of the image. It is like hardware on which the image gets executed/runs. All the snapshot's will be executed within the containers.

So to simplyfy we can say that images are like softwares that run inside the container's hardware.

### Deploying a simple tomcat application using Docker :

To work on this request we need to do the following on our machine:

- Install docker.
- Create image with tomcat and our webapp
  - Dockerfile
    - ubuntu OS image.
    - tomcat is needed to be installed.
    - webapp to be added.
- Deploy our image in a container.
- Connect to the tomcat service running on Docker.


#### Install Docker

This tutorial is created for ubuntu 16.04, incase you are using any other OS, please refer to [official docker documentation](https://docs.docker.com/install) and select the required flavour.

For ubuntu 16.04 follow the following steps :

1. Update the apt package index:
    
    > $ sudo apt-get update

2. Install packages to allow apt to use a repository over HTTPS:
    
    > sudo apt-get install apt-transport-https ca-certificates curl software-properties-common

3. Add Docker’s official GPG key:
    
    > $ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
    
4. Use the following command to set up the stable repository. 
    
    > $ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"

5. Update the apt package index:
    
    > $ sudo apt-get update

6. Install the latest version of Docker CE
    
    > $ sudo apt-get install docker-ce
    
Now, your docker is installed in your ubuntu 16.04 machine and ready to be tested.

Verify that Docker CE is installed correctly by running the *hello world* image.
    
    > $ sudo docker run hello-world
    
This command downloads a test image and runs it in a container. When the container runs, it prints an informational message and exits.

Docker CE is installed and running. The docker group is created but no users are added to it. **You need to use sudo to run Docker commands.** If you wish to not use sudo to run Docker commands then follow the steps from [this link.](https://docs.docker.com/install/linux/linux-postinstall/)

Next : [Create your first image](https://github.com/vipul-gupta13/docker/blob/master/docs/Create_your_first_image.md)
