## Creating containers from Custom Images

### Task 1: Automation - Using Dockerfile to build docker image.
```
vi Dockerfile
```
```Dockerfile
FROM ubuntu
RUN apt update && apt install wget curl tree -y
```
```
docker build -t ubuntu:Dockerfile .   
```
```
docker image ls
```
To check if multiple images can be built from same Dockerfile, we build another image as well
```
docker build -t ubuntu:Dockerfile1 .
```
```
docker image ls
```
```
docker run -it --name ct3 ubuntu:Dockerfile
```
