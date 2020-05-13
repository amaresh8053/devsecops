# devsecops docs

#Jenkin Docker Setup

version '2.1'
services:
	jenkins:
		images:'amrit96/jenkins:late'
		user:"${UID}:${GID}"
		ports:
			- '80:8080'
			- '443:8443'
			- '50000:50000'
		volumes:
		- './jenkins_data:/var/jenkins_home'
		- /var/run/docker.sock:/var/run/docker.sock
		- /usr/bin/docker:/usr/bin/docker
		- /usr/lib/x86_64-linux-gnu/libltdl.so.7:/usr/lib/x86_64-linux-gnu/libltdl.so.7
