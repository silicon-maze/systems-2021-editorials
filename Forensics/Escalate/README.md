# **Escalate**

Category: Forensics

Author: Balajinaidu V

Answer / Flag: `a-304`

## Problem Statement

Get binod's room number.

Answer format: room.no eg. if 289-b is the room no then 289-b is the answer

A Docker Image has to be pulled for this challenge. You can explore cloud based environments if installing docker locally seems too much :)

Resource: https://medium.com/@deepakshakya/beginners-guide-to-use-docker-build-run-push-and-pull-4a132c094d75


## Relevant files / links

`docker pull balajinaidu/binod:latest`


## Solution

Run the docker container to get a shell `docker run -it bin/sh balajinaidu/binod`. Generally while creating a user in linux it asks for details like full name, room no, mobile no. These details are stored in etc/passwd file. But only root user has access to this file. We need to escalate the user to root privelage. There's a file called .notsecret in home/binod directory. Opening that we get a clue '$SOOPAR_SECRET', looks like some environment variable, so running `echo $SOOPAR_SECRET` echoes the root password. switch to root user with the obtained password and cat the etc/passwd to file to obatin the user details of binod. To understand etc/passwd file structure check [this](https://linuxize.com/post/etc-passwd-file/), a-304 is the room no.
