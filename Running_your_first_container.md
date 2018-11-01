# Running your first Container

Now we have created our image, its time to spin up a container with our *my_tomcat:latest* image and see our containerized tomcat application in action.

To create a new container with our image execute the below command :

```
sudo docker run -d -p 8080:8080 my_tomcat:latest
```

This command will start a new container with your tomcat running. But before checking out other things, lets first understand the command.

```
sudo docker      : will call the docker process {you already knew it ;)}
run              : this command starts up the container.
-d               : to spinup the container in detached mode (or we can say container will keep on running in background as a service)
-p               : for port mapping <hostPort>:<containerPort>, because you can not directly access container, so mapping is required
my_tomcat:latest : image name from which you want to spinup a container.
```

The output of the above command will be a number, which is the docker container id which can be used in future to perform actions on that container.

Now your docker container is up and running, you can verify that by executing the following command :

```
sudo docker ps
```

This will show 
