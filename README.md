# Spaceship_Titanic_MLOps_Project

**Youtube Playlist** : [Link here](https://www.youtube.com/playlist?list=PLaiyLZ9Xs1bzu1G0nWERv5gECjuoJUXVR)

Predict which passengers are transported to an alternate dimension

We will be concentraining on MLOps part only, topics like feature engineering, trying alternate models are given less importance.


## AWS
1. Create a iam user with following policies

    a. AmazonEC2ContainerRegistryFullAccess

    b. AmazonEC2FullAccess

2. Create a new keyvalue pair under security credentials and save the file

3. Now create ECR repo and store the URL

    306093656765.dkr.ecr.us-east-1.amazonaws.com/spaceship

### Go to EC2
- create keyvalue pair if u want to access through putty.
Allow HTTP and HTTPs traffic

### Install docker

    sudo apt-get update -y

    sudo apt-get upgrade

    curl -fsSL https://get.docker.com -o get-docker.sh

    sudo sh get-docker.sh

    sudo usermod -aG docker ubuntu

    newgrp docker

## Now Goto Github
- Go to Actions -> Runners -> new self hosted runner
- Execute all commands for linux machine as we selected it

- While entering name of runner give "self-hosted" runner

## Github secrets

AWS_ACCESS_KEY_ID=

AWS_SECRET_ACCESS_KEY=

AWS_REGION = us-east-1

AWS_ECR_LOGIN_URI = only till .com

ECR_REPOSITORY_NAME = nameofrepo


## Values Added in this repo
1. I used different type of dataset, neural network framework used by Krish Naik 
2. I have introduced a db connection in pipeline which is cassandra db
3. I have used torchserve to deploy with onnx
4. I tried using docker-compose and communicating with docker containers for serving api and running flask separately but
there was dependency on transfering onnx model from training part to torch serve container so i was not able to deploy two separate services. 

References:
- Krish Naik Videos
- https://github.com/dimitreOliveira/torchserve_od_example/tree/main
