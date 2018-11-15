## What is a container?
Container can be summed up as ~~mini computers~~ or I should say mini operating systems, that have all the software dependencies, packages & environment settings that required to run your application flawlessly. It is like creating a service for your application, that can be installed and used whenever and wherever you want. And, you can have multiple containers in a single machine and containers are completely isolated from one another as well as from the host machine.

Also, containers unlike VM's use the host machine OS kernel. 

Here you may ask, isn't that everything that a virtual machine provides, then why should I use containers, so to get the answer of this question, I would say "*Go google it*".

## Why containers should be used?
Instead of writing a very big code for your complete application, it would be better to break that monolithic code into multiple micro services that can work independently. This will help you in following ways :

  - Easy to maintain your application.
  - You can easily upgrade different components, without hampering the whole application.
  - Creating micro-services lets you find faults in your code easily, as it is better to find error in 100 lines of code, instead of findings errors in 1000 lines of code.
  - Even the QA can perform his/her testing with ease.
  - Scaling up/down the application becomes much easier as you can increase/decrease the number of instances of required micro-services as and when required.
  - I can provide you 10 more benefits of breaking you application in micro-services, but I think you must have got the flavour of what I am trying to convey.
  
  So, once your application is broken in multiple micro-services, we need to find a way to port (**pun intended**) our application/micro-services from dev cluster to prod cluster, without worrying about the dependecies and environment settings. 
  
  To save the day, and fulfill this request, containers came in handy to create your portable micro services.

Next : [Docker Basics](https://github.com/vipul-gupta13/docker/blob/master/docs/Docker_Basics.md)
