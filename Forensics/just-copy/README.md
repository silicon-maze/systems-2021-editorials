# **Just Copy**

Category: Forensics

Author: Balajinaidu V

Answer / Flag: `MAZE{N1CELY_COP1ED}`

## Problem Statement

Binod always keeps a backup copy of important files. But in frustration he deleted all the files now, can you find any 'copy' in the docker image?

A Docker Image has to be pulled for this challenge. You can explore cloud based environments if installing docker locally seems too much :)


## Relevant files / links

Pull the docker image using `docker pull balajinaidu/binod:latest`

## Solution

Run `docker run -it bin/sh balajinaidu/binod:latest` to get a shell, in the home directory of user binod we find that .copy.png file is hidden(`ls -la` command reveals it), but we can't view the image in the docker container. We have to get the image to our local machine. We can transfer files by either running a simple http server on the victims machine or use scp if ssh is allowed or use ftp. But in this case since the container is running locally we can use `docker cp container_id:path/in/container path/in/local` to transfer the files between container and host machine. So running `docker cp <replace with your container id>:home/binod/.copy.png .` on a new tab of terminal,while the container is still running transfers the image from container to local machine. Open the image to view the flag.
To obtain the container id, run `docker ps -a` in a new terminal while the docker container is running.
