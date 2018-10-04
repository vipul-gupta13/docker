## What is Docker?
Docker is a software bucket comprising everything necessary to run the software independently. It is one of the containerization software, that helps you create containers for your micro-services.

### Lets start.
I hope, by now you must have got an idea of containers and why are they necessary.
To get started with docker, keep the following things in mind :

- Docker have two major components :
  - Image 
  - Container

Image : A docker image is like any other image like that of OS'es with all the required softwares and configuration pre-installed in it.
Container : As the name suggest, container works as the outer shell(in literal terms) of the image. It is like hardware on which the image gets executed.

So to simplyfy we can say that images are like softwares that run inside the containers hardware.

Deploying a simple tomcat application using Docker :

To work on this request we need to do the following on our machine:

- Install docker.
- Create image with tomcat and our webapp
  - Dockerfile
    - ubuntu OS image.
    - tomcat is needed to be installed.
    - webapp to be added.
- Deploy our image in a container.
- Connect to the tomcat service running on Docker.


Docker provide a base image for all kind of OS's, so that they can be used as and when required.
