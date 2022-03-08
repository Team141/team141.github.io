---
title: Docker History
author:
  name: Team141
  link: https://github.com/Team141
date: 2022-03-08 11:33:00 +0530
categories: [Docker, Docker Build]
tags: [Docker, Dockerbuild, Dockerfile]
math: true
mermaid: true
pin: false
---


### Today's Assignment

>**Docker File** for building a *Docker Container* for  **Apache2**

 `Inline Code`.

### Dockerfile

 Copy of below code into file named called `Dockerfile` ('D' must be capital).


```
FROM ubuntu:18.04
LABEL "Project"="LilFasion"
ENV DEBIAN_FRONTEND=noninteractive
RUN apt update
RUN apt install apache2 -y
WORKDIR /var/www/html
#COPY lilfasion.tar.gz /var/www/html
ADD lilfasion.tar.gz /var/www/html
CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
RUN service apache2 restart
VOLUME /var/log/apache2
EXPOSE 80

```
{: .nolineno}


> **Note**: Copy of above code into file named called `Dockerfile` ('D' must be capital).
{: .prompt-info }

---
#### Download following file 

[lilfasion.tar.gz](./_data/lilfasion.tar.gz)



> **Note**: Please place `Dockerfile` and `Archive file` in one folder and build Docker container from same parent folder
{: .prompt-info }

---

### History to build container from Docker File

```console
  # system update
  
  sudo apt-get update

  #install docker in ubuntu

  sudo apt-get install     ca-certificates     curl     gnupg     lsb-release
  echo   "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
    $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
  sudo apt-get update
  sudo apt-get install docker-ce docker-ce-cli containerd.io
  
  #test docker installation

  sudo systemctl status docker
  sudo docker run hello-world
  sudo docker ps
  sudo docker ps -a
  sudo docker images

  #adding sudo permissions to user for docker
  sudo vim /etc/group

  ### Logout and Login ###
  id
  docker images
  docker ps
  docker ps -a
  docker run --name web01 -p 9070:80 -d nginx
  docker ps
  docker logs web01
  docker ps
  docker images
  docker stop web01
  docker images
  docker ps
  docker ps -a
  docker start web01
  docker restart web01
  clear
  docker stop web01
  docker rm web01
  docker ps
  docker rmi nginx:latest 
  docker images
  docker rmi images
  docker rmi feb5d9fea6a5
  docker ps -a
  docker rm e85182a36757
  docker rmi feb5d9fea6a5
  docker images
  docker pull mysql:5.7
  clear
  docker inspect mysql:5.7 
  docker run -d -P mysql:5.7 
  docker ps
  docker ps -a
  docker logs 081559b2d468
  docker run -d -P
  docker logs 081559b2d468
  docker run -d -P -e MYSQL_ROOT_PASSWORD=secretpass mysql:5.7 
  docker ps
  docker volume
  docker volume create vprodata
  docker volume ls
  docker run -d -P -v vprodata:/var/lib/mysql
  docker run -d -P -v vprodata=/var/lib/mysql -e MYSQL_ROOT_PASSWORD=secretpass mysql:5.7 
  docker ps
  docker volume ls
  docker stop 6770957511b6
  docker rm 6770957511b6
  docker ps
  docker volume ls
  docker exec admiring_tu ls /var/lib/mysql
  docker run -d -P -v vprodata=/var/lib/mysql -e MYSQL_ROOT_PASSWORD=secretpass mysql:5.7 
  docker volume ls
  sudo ls /var/lib/docker/
  sudo ls /var/lib/docker/volumes
  sudo ls /var/lib/docker/volumes/vprodata
  sudo ls /var/lib/docker/volumes/vprodata/_data
  docker ps
  docker stop 6ed5dceba392 750611cb2e44
  docker rm 6ed5dceba392 750611cb2e44
  docker ps -a
  docker stop 081559b2d468
  docker rm 081559b2d468
  docker ps -a
  docker run -d -P -v vprodata=/var/lib/mysql -e MYSQL_ROOT_PASSWORD=secretpass mysql:5.7 
  docker exec /var/lib/mysql
  docker ps
  docker exec youthful_mendel /var/lib/mysql
  docker exec youthful_mendel ls /var/lib/mysql
  sudo ls /var/lib/docker/
  sudo ls /var/lib/docker/volumes/
  sudo ls /var/lib/docker/volumes/vprodata/
  sudo ls /var/lib/docker/volumes/vprodata/_data
  docker logs youthful_mendel
  docker run -d -P -e MYSQL_ROOT_PASSWORD=secretpass mysql:5.7
  docker volume create vprodata
  docker volume ls
  docker run -d -P -v vprodata:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=secretpass mysql:5.7
  docker ps
  docker exec jovial_bhaskara ls /var/lib/mysql
  ls
  sudo ls /var/lib/docker/volumes
  sudo ls /var/lib/docker/volumes/vprodata/_data
  docker exec jovial_bhaskara ls /var/lib/mysql
  docker stop jovial_bhaskara
  docker rm jovial_bhaskara
  sudo ls /var/lib/docker/volumes/vprodata/_data
  docker ps -a
  clear
  mkdir code
  touch code/file{1..5}.pyp
  ls code/
  docker run -d -P -v /home/ubuntu/code:/code nginx
  docker ps
  docker exec vigorous_tesla ls 
  docker exec vigorous_tesla ls /code
  docker inspect vigorous_tesla
  docker image
  docker images
  docker inspect c919045c4c2b
  clear
  ls 
  rm -rf code/
  ls
  docker ps -a
  docker stop youthful_mendel focused_roentgen vigorous_tesla
  docker rm youthful_mendel focused_roentgen vigorous_tesla
  docker rmi *
  docker rmi --help
  docker images
  docker rmi mysql:5.7 nginx:latest 
  docker images
  clear
  mkdir antique
  cd antique/
  cd 
  wget https://www.tooplate.com/zip-templates/2126_antique_cafe.zip
  ls
  unzip 2126_antique_cafe.zip 
  sudo apt install unzip
  clear
  unzip 2126_antique_cafe.zip 
  clear
  cd 2126_antique_cafe/
  tar cvzf web01.tar.gz *
  clear
  ls
  mv web01.tar.gz ../
  ls
  cd
  ls
  rm -rf 2126_antique_cafe*
  rm antique/
  rm-rf  antique/
  rm -rf  antique/
  ls
  mkdir antique
  mv web01.tar.gz antique/
  cd antique/
  ls
  vim Dockerfile
  docker build -t --help
  docker build  --help
  docker build -t antiqueweb ..
  docker build -t antiqueweb .
  vim Dockerfile
  docker build -t antiqueweb .
  clear
  docker build -t antiqueweb .
  clear
  docker images
  docker rmi ad94ae422a95
  docker images
  docker inspect antiqueweb
  docker run -d -p 7080:80 antiqueweb
  docker ps
  tar xvzf web01.tar.gz 
  ls
  mv web01.tar.gz Dockerfile ../
  ls
  rm -rf *
  ls
  mv ~/web01.tar.gz .
  mv ~/Dockerfile .
  ls
  docker logs
  docker ps
  docker logs hungry_chaplygin
  docker stop hungry_chaplygin
  docker rm hungry_chaplygin
  docker rmi antiqueweb:latest 
  cat > Dockerfile 
  cat Dockerfile 
  mv web01.tar.gz lilfasion.tar.gz
  ls
  docker build -t web01 .
  docker run -d -p 7080:80 antiqueweb
  docker run -d -p 7080:80 web01
  docker ps -a
  docker logs amazing_germain
  docker run -d -p 7080:80 web01 -h
  docker logs amazing_germain
  docker ps
  docker stop amazing_germain
  docker rm amazing_germain
  docker run -d -h  -p 7080:80 web01 
  docker run -d -P web01:latest 
  docker logs amazing_germain
  docker ps 
  docker logs hardcore_brown
  docker stop hardcore_brown
  docker rmhardcore_brown
  docker rm hardcore_brown
  docker rmi web01:latest 
  docker ps -a
  docker stop e679b42ea4f4
  docker rm e679b42ea4f4
  docker rmi web01:latest 
  ls
  vim Dockerfile 
  docker build web01 .
  docker build -t  web01 .
  docker rmi web01:latest 
  vim Dockerfile 
  docker build -t  web01 .
  docker rmi web01:latest 
  vim Dockerfile 
  docker build -t  web01 .
  docker run -d -p 7070:80 web01
  docker ps
  docker logs vigorous_goldberg
  docker logs vweb01
  docker logs 4e16fa1f787f
  docker stop 4e16fa1f787f
  docker rm 4e16fa1f787f
  docker rmi web01
  vim Dockerfile 
  docker build -t LilFasion:v1 .
  docker build -t LilFasion .
  docker build -t web01 .
  cat /etc/hosts
  ls
  cd antique/
  ls
  vim Dockerfile 
  docker build -t web01 .
  docker images
  docker run -d -p 7080:80 web01:latest 
  docker ps
  docker logs youthful_feynman
  docker ps -a
  docker ps 
  docker stop a5960658ac2b
  docker rm a5960658ac2b
  docker images
  docker login
  docker push kumarradev5/web01
  docker push kumarradev5/web01:latest
  docker push kumarradev5/web01:v1
  docker push kumarradev5/web01
  docker tag web01:latest web01:v1
  docker images
  docker push web01:v1
  docker push kumarrajdev5/web01:v1
  docker push web01:v1
  docker push kumarrajdev5/web01
  docker images
  docker push web01
  docker push kumarrajdev5/web01:v1
  docker push web01
  docker logput
  docker logout
  docker login
  docker push web01
  docker push kumarrajdev5/web01
  docker tag web01:v1 kumarrajdev5/web01:v1
  docker push kumarrajdev5/web01
  docker images
  docker rmi kumarrajdev5/web01:v1 web01:latest web01:v1 
  docker images
  docker rmi ubuntu:latest ubuntu:18.04 
  docker build -t fasionimg .
  docker build -t kumarrajdev5/fasionimg:v1 .
  docker push kumarrajdev5/fasionimg:v1 
  docker images
  docker rmi kumarrajdev5/fasionimg:v1 fasionimg:latest 
  docker images
  docker rmi ubuntu:18.04 
  docker images
  docker run -d -P --name kumar kumarrajdev5
  /
  docker run -d -P --name kumar kumarrajdev5/fasionimg
  docker run -d -P --name kumar kumarrajdev5/fasionimg:v1
  docker run -d -p 7000:80 --name kumar kumarrajdev5/fasionimg:v1
  docker run -d -p 7000:80 --name kumar1 kumarrajdev5/fasionimg:v1
  docker ps
  docker stop kumar
  docker stop kumar1
  docker rm kumar kumar1
  docker rmi kumarrajdev5/fasionimg:v1 
  docker image
  docker images
  cd ..
  history
  history > history.txt
  ls
  cat -n history.txt 
  cat -b history.txt 
  ls
  rm-rf history.txt 
  rm history.txt 
  ls
  history< history.txt
```





