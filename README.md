# static_web

## Install Docker 
$ sudo apt-get update
$ sudo apt install docker.io
$ sudo snap install docker
$ docker --version

## Pull the image from the registry
$ docker pull nginx:latest
$ docker images

## index.html file 
<!DOCTYPE html>
<html>
    <head>

    </head>
    <body>
        Welcome to Learnkarts!
    </body>
</html>

## Dockerfile
FROM nginx
COPY ./index.html  /usr/share/nginx/html/index.html

##To build our custom image.
$ docker build -t webserver .

Deploy the container
$ docker run -it -d -p 8080:80 webserver

To verify container 
$ docker ps

## Install AWS CLI 
$ sudo apt install awscli 
$ aws --version

## Create S3 Bucket
$ aws s3 mb s3://<insert-unique-name-here>
  
To copy index.html filr from local directory to S3 Bucket
$ aws s3 cp "<file-path-here>" s3://<insert-created-bucket-here>

