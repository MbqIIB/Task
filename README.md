# Task 1
Write a Dockerfile (CentOS 6) to install the following in a Docker continer:

Python 2.7
MongoDB - any version
Apache tomcat 7 - running on port 8080 Please include comments at every command explaining what it does. Write the command to run the Dockerfile such that once the container boots, apache tomcat's home page is accessible from the host on port 7080.
Contents

This directory is the build context for the docker image containing Python 2.7, MongoDB 3.4 and Apache Tomcat 7.

'mongodb-org-3.4.repo' file is required for configuring the yum repository to download MongoDB 3.4
'start.sh' scriptis required to ensure both MongoDB and Tomcat servers run simultaneouly
'Dockerfile' to build docker image
Requirements:

Docker >= 17
Instructions:

After cloning the repo  execute the following commands -

 Task-1
To build the docker image,

 docker build -t mytomcat . (don't forget the dot at the end, it implies current directory)
To run a docker container with the built docker image,

 docker run -p 7080:8080 -p 27017:27017 -d --name mytomcatcontainer mytomcat
Optionally, you may attach/ connect to the docker instance using,

 docker exec -it mytomcatcontainer /bin/bash
Now Tomcat server and MongoDB server are accessible from the host on port '7080' and '27017' respectively.

NOTE:-

Python 2.7 interpreter is accessible from within the container as 'python2.7'. Invoking 'python' will bring up Python 2.6 interpreter. Ex:
$ python2.7 --version
Python Python 2.7

$ python --version
Python 2.6.6
All files in this directory should be included in the build context for docker image build to succeed.
