# Docker

### Table of content
- [Docker](#docker)
    - [Table of content](#table-of-content)
  - [Cheatsheet](#cheatsheet)
  - [Installation](#installation)
---

## Cheatsheet

```
$ docker run nginx                                      // This pulls the image with tag 'latest'
$ docker run nginx:1.26                                 // This pulls the image with tag '1.26'

$ docker run -i jglab/testapp                           // This is to have input prompt in the docker container
$ docker run -it jglab/testapp                          // This is to have a pseudo terminal attached to the container to see the prompts

$ docker run -p 8080:5000 jglab/testapp                 // This maps host port to the container port
$ docker run -v /opt/sqlbackup:/var/lib/mysql mysql     // This maps host directory to the container directory

$ docker run -d nginx                                   // Detach the container
$ docker attach <container name/id>                     // Attach the Detached container
$ docker exec nginx cat /etc/hosts

                                                        // To define the dependencies
$ docker run -d --name=redis redis
$ docker run -d --name=webapp  -p 8080:5000 --link redis:redis jglab/webapp

$ docker inspect <container name/id>                    // To get details of the container 
$ docker logs <container name/id>                       // To get logs of the StdOut in the container

$ docker ps -a
$ docker stop <container name/id>
$ docker remove <container name/id>

$ docker pull
$ docker image list
$ docker remove images <image name/id>

$ docker run -e DEBUG_ENABLE=true jglab/mypy


$ docker volume create myVolume
$ docker run -v myVolume:/var/lib/mysql mysql

$ docker run --mount type=bind,source=/myVolume,target=/var/lib/mysql mysql

$ docker network create -driver=bridge --subnet=192.168.192.0/24 custom-network
$ docker network ls

$ docker run --network=custom-network
```

## Installation
