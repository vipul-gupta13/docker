# Creating your First Image

This is the part you have been waiting to work upon, creating your own image.
This is thing that you will be doing over and over again, as this is the heart and soul of docker.

To create a new image, you need to have a **base image** over the top of which you will install your dependencies, set your environment and deploy your application.

### Base Image

Base Image (also called, Parent Image) is like the snapshot of bare OS, that will act as the baseline of your application. Docker provide us with images of all the available distribution of various OS's as images, which are easily and freely available from **_dockerhub_**.

### Docker Hub

Docker hub is like the central publicly available repository of docker images, in which anyone can upload his/her own image, once he/she thinks that the image can be reused by other.
For example:

- you can get images for pre installed software (eg. tomcat, apache2, jenkins, elk, etc. etc.)
- you can images for multiple OS's (eg. ubuntu, fedore, debian, centOS etc. etc.)
- you can get images for pre installed DB's (eg. Mysql, cassandra, mongoDB, etc.)

I would recommend to explore it. [Click here](https://hub.docker.com/explore)

### DockerFile

Dockerfile is like the script, which will execute steps in the order they are written and the end result will be the image that you want to create.

A basic template of dockerfile will look like :

```
  get base image.
  install dependencies.
  set environment.
  deploy your application.
```
