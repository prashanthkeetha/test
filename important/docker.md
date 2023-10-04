* Docker: Docker is a container based application used to run microservices. 
container: container is an isolated area created by container engine have lean OS and application runs inside the container.
By using docker we can build and package the application.
* For nodejs and dotnet we to place the code inside the server. 
each container get
1.CPU 
2.RAM
3.IP ADDRESS
* When we install docker we get docker engine 
1. docker Engine have:
a. Client and server.
After installing docker we get the client running if we want to run the server, we need the command <sudo usermod -aG docker <username> >
-a is a active user G is a Group of docker
--- (By using 1 IMAGE we can RUN Multiple Containers)
After entering the command we need the exit form the VM and login back.
* Tu see weather the docker engine is working we need enter command <docker info> . 
* To run the container we use images.
* To see the list of images command <docker image ls > to see all use <docke image ls -a>
* In docker for the image there will be <Repository (name of image)> and tag <version> 
* to pull th image from docker registry we use <docker image pull <imaganame:tag> >
* we build the images to run containers.
* To push the image into the docker registry <docker image push <iamgename:tag> >,
* To see the running images in the docker we use <docker image ls>.
* To run the container with port number we use the command <docker container run -it -p <portno> name of the image:tag >,<docker container -d -P image name:tag>
-it is a interactive mode where we go into the container as a root user.
-d uses for distractive mode where we can see only the container id.
* To remove the images from <docker image rm (image-name or id)> (or) To remove multiple images at once <docker image rm -f $(docker image ls -q )>
* To remove the containers command <docker container rm (container-id)> (or) 
* To remove multiple containers at <docker container rm -f $(docker container ls -a -q)>
* Every container has its own 
1. Network ip address.
2. CPU
3. RAM
4. Filesystem share
* To see the utilization of RAM we use <docker stats>, By using the command we can see 
<CONTAINER ID   NAME      CPU %     MEM USAGE / LIMIT   MEM %     NET I/O   BLOCK I/O   PIDS>
* To go inside the container we can use the command <docker container run -it image:tag /bin/bash (or) /bin/sh> .

* Docker filesystem  is ( var/lib/docker ) where the docker files are stored . 
* Namespace is a isolated area, which have storage and we can mount the network    interface in the namespace. 
* By using Cgroups kernal can control the storage impose limits on the RAM.
* If we want to run the web application we need the middleware <webservers (apache,Tomcat, springboot have jetty server to run the web application and jboos) > .
* To write the dockerfile we need this instructions.
1. FROM : By using this we take the base image with required dependencies.
2. RUN: By using run we can install the required data
3. ADD: By using this instruction we can take the source of the package and Destination to store the file.
4. EXPOSE: It is used to expose the port.
5. CMD: Used to run the package file as the /root user. 
6. COPY: Use this instruction to copy data from thr local machine
7. ADD: By using this instruction we can copy the data from local and web. 
8. ARG: where we pass the arguments and tags if we use.<ARG Branch = required branch name on which the dependencies are there> and we can pass many things
9. ENV: it is used to pass environment variables dynamicall in command <docker container run -e (statement) -it imagename:tag /rootdirectory >
* Some appliactions run on the server by starting server we can start the container <systemctl start (servername)>
* Docker image is aa collection of image layers.
* Docker layers are created by adding the instruction to the (dockerfile).
* Docker image layer are stored in docker filesystem (or) root /var/lib/docker.
* docker image have READ only LAYER but, After creating the container the docker container have read write layer.    
* To inspect the image <docker image inspect> 
* By using <docker logs (container id)> we can see the container information.
# docker have multistaged dockerfile.
* In the first we is used to build the package and in the second or last stage contain we used to build the image.
* Afterbuilding the package in the first stage by USING <COPY (we can capy the package from first to second stage)> 
# COPY --from = name give to the firststage or name given topackage building stage and src and dest

###
# Docker Volumes:

# Docker volumes are used to persist the data even after the container is deleted.
* docker container has a read write layer when ever we make changes in the image layer it stores the changing data in the container read write layer.
* Any changes we do inside the container it will not effect to the image layer it only makes chnages in the container.
* the life time of the chnages we make in the container is as long as the container is works if the container is deleted the data in the container is lost.
* Docker volumes are three types 
# Bind mount
command <docker container run -d --mount "type=bind,source=/tmp/cont-temp,target=/tmp" --name (by using --name we can name the container) image name>
* By using docker bind mount we can mount the storage to existing folder in host.
* If we clean the data we will lose it.
# volumes
# tmpfs 

* the command <exec> which means run the command in the running container.

###
Questions:
----------
1. What is containerd
------------------
Ans. It is specification how container should be. Here containers run by using containerd and it calls runc to run containers by using images.
2.What is OCI runc
--------------
Ans. It is image specification where we can run the containers.
3.What is shim
4.How do we take base image
5.What is entrypoint
6.How to start service.
