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

Create a test directory and inside that directory create a file named 'Dockerfile'.
So the Dockerfile to install jdk1.8 and tomcat on a ubuntu base image will look like :

```
# to get ubuntu base image
FROM ubuntu:latest
MAINTAINER vipulgupta13@gmail.com

# to update the packages and installing wget
RUN apt-get -y update \
    && apt-get -y install wget

# to download the tar of jdk1.8
RUN wget --no-check-certificate -c --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u191-b12/2787e4a523244c269598db4e85c51e0c/jdk-8u191-linux-x64.tar.gz -O /tmp/java8.tar.gz

# to download the tar of tomcat7
RUN wget http://apache.uib.no/tomcat/tomcat-7/v7.0.91/bin/apache-tomcat-7.0.91.tar.gz -O /tmp/tomcat.tar.gz

RUN mkdir /usr/local/tomcat \
    && mkdir /usr/local/java

RUN cd /tmp \
    && tar xvfz tomcat.tar.gz \
    && tar xvfz java8.tar.gz
    
RUN cp -Rv /tmp/apache-tomcat-7.0.91/* /usr/local/tomcat/ \ 
    && cp -Rv /tmp/jdk1.8.0_191/* /usr/local/java/

# Creating a softlink with java
RUN ln -s /usr/local/java/bin/java /usr/bin/java

# starting the tomcat whenever the container for this image is started.
CMD /usr/local/tomcat/bin/catalina.sh run
```

This is pretty much self explainatory dockerfile which covers the complete flow which will be required to create a complete image with java 8 and tomcat 7 installed and running.

Once you save the 'Dockerfile', in the same directory, please execute the below command to build the image :

docker build -t <name_of_image>:<tag_of_image> <path_to_Dockerfile>

```
docker build -t my_tomcat:latest .
```
