# -------------------------------- START CREATE DOCKER --------------------------------------------------
# 1.0 create Droplet+Docker  in https://cloud.digitalocean.com/
# ---  Centos 7 x64 > $18
# 2.0 Open your teminal
# 3.0 ssh root@IP _address
# --- [root@Docker ~]# 
# 4.0 [root@Docker ~]# yum install wget -y
# 5.0 [root@Docker ~]# wget -qO - https://get.docker.com/  | sh
# --- Public key for docker-buildx-plugin-0.10.4-1.el7.x86_64.rpm is not installed
# Importing GPG key 0x621E9F35:
 # Userid     : "Docker Release (CE rpm) <docker@docker.com>"
 # Fingerprint: 060a 61c5 1b55 8a7f 742b 77aa c52f eb6b 621e 9f35
#  From       : https://download.docker.com/linux/centos/gpg
# 6/0 [root@Docker ~]# systemctl start docker
# 7.0 [root@Docker ~]# systemctl enable docker
# --- Created symlink from /etc/systemd/system/multi-user.target.wants/docker.service to /usr/lib/systemd/system/docker.service.
# 8.0 [root@Docker ~]# docker version
# 9.0 [root@Docker ~]# systemctl status docker
# --- ● docker.service - Docker Application Container Engine
# ---    Loaded: loaded (/usr/lib/systemd/system/docker.service; enabled; vendor preset: disabled)
# ---    Active: active (running) since Sun 2023-04-16 18:19:03 UTC; 21min ago
# 10.0 [root@Docker ~]# docker ps                        # Show running container 
# --- CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
# 11.0 [root@Docker ~]# docker ps -a                     # Show all container    
#
# -------------------------------- START CREATE DOCKER ------------- UP -------------------------------------
#
#
#-
# in TEAM-SPRING-PETCLINIC >  > Open file "Dockerfile"
# 1.0 OPEN folder "docker"
# 2.0 in folder "docker" Open file "Dockerfile"
# 3.0 Working in file "Dockerfile"
#
# ---------------------------- COPY AND PASTE from https://github.com/spring-projects/spring-petclinic ------------------------
#
# git clone https://github.com/spring-projects/spring-petclinic.git
# cd spring-petclinic
# ./mvnw package
# java -jar target/*.jar                                         # image create by java
#
# go to https://hub.docker.com/  > looking for java > DEPRECATED > openjdk > tag=21-slim
FROM openjdk:21-slim
# check image = "openjdk:21-slim" really working 
#
## 1.0 [root@Docker ~]# docker run -it openjdk:21-slim /bin/bash
## --- Status: Downloaded newer image for openjdk:21-slim
## --- root@cc02bd8270b2:/# 
#
# 1.0 TsyrenD@ip-10-0-101-208 Team5-spring-petclinic]$ docker run -it openjdk:21-slim /bin/bash  --- created new container and attache it to it
# --- Status: Downloaded newer image for openjdk:21-slim
# --- root@567bcc774a02:/# 
#
## 2.0 root@cc02bd8270b2:/# git clone
## --- bash: git: command not found                          # don't know command "git clone"
#
# 2.0 root@567bcc774a02:/#  git clone
# --- bash: git: command not found                           # don't know command "git clone"
# 3.0 root@567bcc774a02:/#  apt-get
# --- apt 2.2.4 (amd64)                                      # command "apt-get " available , you can up get upgates
# 
## 3.0 root@cc02bd8270b2:/# apt-get
# --- apt 2.2.4 (amd64)                                          # command "apt-get " available , you can up get upgates
#
# 4.0 root@567bcc774a02:/# apt-get update
# --- Get:6 http://deb.debian.org/debian bullseye-updates/main amd64 Packages [14.6 kB]
# --- Fetched 8643 kB in 1s (5987 kB/s)                           
# --- Reading package lists... Done
#
## 4.0 root@cc02bd8270b2:/# apt-get update
## -- Get:6 http://deb.debian.org/debian bullseye-updates/main amd64 Packages [14.6 kB]
## --- Fetched 8643 kB in 1s (5987 kB/s)                           
## --- Reading package lists... Done
# 
# 5.0 root@567bcc774a02:/# apt-get install git
# --- After this operation, 99.4 MB of additional disk space will be used.
# --- Do you want to continue? [Y/n] y
# --- Setting up git (1:2.30.2-1+deb11u2) ...
# --- Processing triggers for libc-bin (2.31-13+deb11u5) ...
# 
## 5.0 root@cc02bd8270b2:/# apt-get install git
## --- After this operation, 99.4 MB of additional disk space will be used.
## --- Do you want to continue? [Y/n] y
## --- Setting up git (1:2.30.2-1+deb11u2) ...
## --- Processing triggers for libc-bin (2.31-13+deb11u5) ...
## --- root@cc02bd8270b2:/# 
#
# -------------------------- Added command ----- View -------------------
# FROM openjdk:21-slim
# RUN apt-get update && apt-get install git -y                                                 # added
# RUN git clone https://github.com/spring-projects/spring-petclinic.git
# cd spring-petclinic
# ./mvnw package
# java -jar target/*.jar   
# ------------------------------------------------------------------------
#
# 1.0 Open folder docker > click "open in integrated Terminal"
# --- [TsyrenD@ip-10-0-101-208 docker]$
# 2.0 [TsyrenD@ip-10-0-101-208 docker]$ ls
# --- Dockerfile
# 3.0 [TsyrenD@ip-10-0-101-208 docker]$ git clone https://github.com/spring-projects/spring-petclinic.git
# --- Resolving deltas: 100% (3626/3626), done.
# --- Updating files: 100% (111/111), done.
#
# --- i can see in folder "docker" a new folder "spring-petclinic"
# RUN apt-get uptate && apt-get install git -y                   # if command "git clone" don't work  # DELETE > Need a lot of memory in container
# RUN git clone https://github.com/spring-projects/spring-petclinic.git                               # DELETE > Need a lot of memory in container
# COPY all command RUN & RUN from top line >>>>> inside spring-petclinic /app 
#
# 4.0 COPY spring-petclinic /app          # spring-petclinic=application code
COPY spring-petclinic /app
#
# ---------------------------- NEW VIEW --------------------------------------------
# FROM openjdk:21-slim
# COPY spring-petclinic /app
# cd spring-petclinic
# ./mvnw package
# java -jar target/*.jar
# ------------------------------------------------------------------------------------
#
# "cd " command don't working > cd spring-petclinic > change to WORKDIR >  > WORKDIR /app
WORKDIR /app
#
# "./mvnw package" CHANGE to " RUN ./mvnw package "
RUN ./mvnw package
#
# ---------------------------- NEW VIEW --------------------------------------------
# FROM openjdk:21-slim
# COPY spring-petclinic /app
# WORKDIR /app
# RUN ./mvnw package
# java -jar target/*.jar
# ------------------------------------------------------------------------------------
#
# ------- EXPLAIN how WORKING commands "RUN ./mvnw package" and "java -jar target/*.jar" ------ TESTING ----- example for Troubshouting --
# 
# 1.0 [TsyrenD@ip-10-0-101-208 Team5-spring-petclinic]$
# 2.0 [TsyrenD@ip-10-0-101-208 Team5-spring-petclinic]$ git clone https://github.com/spring-projects/spring-petclinic.git    # in root
# --- Resolving deltas: 100% (3627/3627), done.
# --- Updating files: 100% (111/111), done.
# 4.0 [TsyrenD@ip-10-0-101-208 Team5-spring-petclinic]$ ls
# --- docker  README.md  spring-petclini
# 3.0 [TsyrenD@ip-10-0-101-208 Team5-spring-petclinic]$ docker run -d -it --name java1 -v ~/spring-petclinic:/app openjdk:21-slim /bin/bash          # Mount file /spring-petclinic:/app in container # in create container with image=openjdk:21-slim
# --- 943f5b096da6aba5616a719e2add851c024256edca77d54710e8a45959e83a12
# 4.0 [TsyrenD@ip-10-0-101-208 Team5-spring-petclinic]$ docker exec java1 ls /app  
# --------------------------------- see all code ------------------------------
# --- LICENSE.txt
# --- build.gradle
# --- docker-compose.yml
# --- gradle
# --- gradlew
# --- gradlew.bat
# --- mvnw
# --- mvnw.cmd
# --- pom.xml
# --- readme.md
# --- settings.gradle
# --- src
# --- target
# --------------------------------- see all code -UP -----------------------------
# 
#
## ------- EXPLAIN how WORKING commands "RUN ./mvnw package" and "java -jar target/*.jar" ------ TESTING ----- example for Troubshouting --
##
## --- TESTING IN TERMINAL 
## 1.0 [root@Docker ~]# docker run -d -it --name java2 -v ~/spring-petclinic:/app openjdk:21-slim /bin/bash 
## --- a76d337c6d8fc197a5f9a69208ac0f26442b6528d8146cf659137661b7b43670
## 2.0 [root@Docker ~]# docker exec java2 ls /app
## # --------------------------------- see all code ------------------------------
## --- LICENSE.txt
## --- build.gradle
## --- docker-compose.yml
## --- gradle
## --- gradlew
## --- gradlew.bat
## --- mvnw
## --- mvnw.cmd
## --- pom.xml
## --- readme.md
## --- settings.gradle
## --- src
## --- target
# --------------------------------- see all code -UP -----------------------------
#
#


# ---------------------------------  HOW DELETE Container ---------------------
# [TsyrenD@ip-10-0-101-117 dacker]$ docker rm --force java2              # if you have trash container "java2"
#
# ---------------------------------  ATTACH CONTAINER -------------------------
#
# 1.0 TsyrenD@ip-10-0-101-208 Team5-spring-petclinic]$ docker attach java1
# --- root@943f5b096da6:/# 
# 2.0 root@943f5b096da6:/# ls /app                                # show code 
# --- show code > LICENSE.txt  build.gradle  docker-compose.yml  gradle  gradlew  gradlew.bat  mvnw  mvnw.cmd  pom.xml  readme.md  settings.gradle  src  target
# 
#  --------------------------------- RUN ./mvnw package -------------------
# 
# 1.0 root@943f5b096da6:/# cd /app
# --- root@943f5b096da6:/app# 
# 2.0 root@943f5b096da6:/app#  ./mvnw package                 " waiting 2 min"  >>>>> created ".jar" file
# --- root@943f5b096da6:/app#  ./mvnw package  
# --- [INFO] Scanning for projects...
# ---  -------
# --- 
# --- [INFO] BUILD SUCCESS   ---------------------     # if working anything correctly > BUT > if you paste wrone image=FROM openjdk:21-slim > "BUILD UNSUCCESS" 
# --- root@943f5b096da6:/app# 
# 
# ---------------------------- NEW VIEW --------------------------------------------
# FROM openjdk:21-slim
# COPY spring-petclinic /app
# WORKDIR /app
# RUN ./mvnw package
# java -jar target/*.jar
# ------------------------------------------------------------------------------------
#
#------------------------ RRUNNING -------- java -jar target/*.jar -------------------------
# 1.0 root@943f5b096da6:/app# java -jar target/*.jar
# 2.0 CONTROL+C                            # CANCELED -because image working
# --- root@943f5b096da6:/app# 
# 3.0 root@943f5b096da6:/app# ls target/*.jar
# --- target/spring-petclinic-3.0.0-SNAPSHOT.jar  ------------------ this is a really name " .jar" file
# --- Change >["java" "-jar" "target/*.jar"] > CMD["java", "-jar", "target/spring-petclinic-3.0.0-SNAPSHOT.jar"] 
# CMD ["java", "-jar", "target/spring-petclinic-3.0.0-SNAPSHOT.jar"] 
#
# ---------------------------- NEW VIEW --------------------------------------------
# FROM openjdk:21-slim
# COPY spring-petclinic /app
# WORKDIR /app
# RUN ./mvnw package
# CMD ["java", "-jar", "target/spring-petclinic-3.0.0-SNAPSHOT.jar"] 
# ------------------------------------------------------------------------------------
#
CMD ["java", "-jar", "target/spring-petclinic-3.0.0-SNAPSHOT.jar"] 
#
# 0.0 [TsyrenD@ip-10-0-101-208 docker]$ docker build -t "tdambaev/petclinic:v1" . 
# --- Successfully built 6083777dff61
# --- Successfully tagged tdambaev/petclinic:v1
# 1.0 [TsyrenD@ip-10-0-101-208 docker]$  docker build -t "tdambaev/petclinic:v2" .
# --- Successfully built 01c90e6a4a02
# --- Successfully tagged tdambaev/petclinic:v2# 
# 2.0 [TsyrenD@ip-10-0-101-208 Team5-spring-petclinic]$ docker images
# --- REPOSITORY                                                                               TAG                       IMAGE ID       CREATED          SIZE
# --- tdambaev/petclinic                                                                       v2                        01c90e6a4a02   59 seconds ago   717MB
# --- tdambaev/petclinic                                                                       v1                        ef51eba53e35   49 minutes ago   717MB    
# 3.0 [TsyrenD@ip-10-0-101-208 Team5-spring-petclinic]$ docker run -d -p 8080:8080 tdambaev/petclinic:v2
# --- 68599ad0ce66bc0365dfded524b9135a706a4af4743ae79f3d3e1dec7f6f6062
# 4.0 Command "SAVE FILE"
# 5.0 [TsyrenD@ip-10-0-101-208 Team5-spring-petclinic]$ docker ps
# --- CONTAINER ID   IMAGE                   COMMAND                  CREATED              STATUS              PORTS                                       NAMES
# --- 68599ad0ce66   tdambaev/petclinic:v2   "java -jar target/sp…"   About a minute ago   Up About a minute   0.0.0.0:8080->8080/tcp, :::8080->8080/tcp   friendly_robinson
# 6.0 [TsyrenD@ip-10-0-101-208 Team5-spring-petclinic]$ docker run -d -it tdambaev/petclinic:v1 /bin/bash
# --- 001255d70c794513466a63b0bf4b79c783b2eecf22b746dd53014956857f0722
# 7.0 [TsyrenD@ip-10-0-101-208 Team5-spring-petclinic]$ docker ps
# --- CONTAINER ID   IMAGE                   COMMAND                  CREATED          STATUS          PORTS                                       NAMES
# --- 001255d70c79   tdambaev/petclinic:v1   "/bin/bash"              48 seconds ago   Up 47 seconds                                               gallant_gould
# --- 68599ad0ce66   tdambaev/petclinic:v2   "java -jar target/sp…"   36 minutes ago   Up 36 minutes   0.0.0.0:8080->8080/tcp, :::8080->8080/tcp   friendly_robinson
#
# ----------------------- ONLY TESTING -------------------------------------
# 1.0 TsyrenD@ip-10-0-101-208 Team5-spring-petclinic]$ docker attach 001255d70c79 
# --- root@001255d70c79:/app# 
# 2.0 root@001255d70c79:/app# ls target/
# --- checkstyle-cachefile    checkstyle-header.txt  checkstyle-suppressions.xml  generated-sources       jacoco.exec     maven-status  spring-petclinic-3.0.0-SNAPSHOT.jar           surefire-reports
# --- checkstyle-checker.xml  checkstyle-result.xml  classes                      generated-test-sources  maven-archiver  site          spring-petclinic-3.0.0-SNAPSHOT.jar.original  test-classes


# --------------------------- HOW CHECK ALL CONTAINER -----------------
#
# [TsyrenD@ip-10-0-101-208 Team5-spring-petclinic]$ docker ps -a
#
# --------------------------- HOW CHECK ALL CONTAINER ---- UP -------------


#  ------------------------------------------------------------- TROUBLESHOUTING  DOCKER  CONTAINER ----------------------------------------
#  
# Docker Logs
#   docker logs CONTAINER _ID
# -------------------------------------------------------------- TROUBLESHOUTING  DOCKER  CONTAINER ----------UP------------------------------


# 1.0 root@943f5b096da6:/app# ls target/*.jar
# --- target/spring-petclinic-3.0.0-SNAPSHOT.jar  ------------------ this is a really name " .jar" file
# --- Change >>>> CMD ["java" "-jar" "target/*.jar"] >>>> CMD ["java", "-jar", "target/*.jar"] >>>
# CMD ["java", "-jar", "target/spring-petclinic-3.0.0-SNAPSHOT.jar"] 
#
#
# [TsyrenD@ip-10-0-101-208 docker]$ docker build -t "tdambaev/petclinic:v1" . 
# 




# [TsyrenD@ip-10-0-101-208 Team5-spring-petclinic]$ docker run -d -p 8080:80808 tdambaev/petclinic:v2