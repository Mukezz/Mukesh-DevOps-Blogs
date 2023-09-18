DevOps Blog 3: Packaging Using Maven Plugin and Deploying into AWS API and Azure API

To view the detailed post follow me at LinkedIn https://www.linkedin.com/in/mukesh-kuduva-vivekanandan/

Project: Packaging Using Maven Plugin and Deploying into AWS API and Azure API
Outcome: 
Note: using the same Spring Boot repo that was used in Blog 2.

Following steps are for creating the AWS EC2 instance:
1: Login into AWS console 
2: Spin up the free tier EC2 instance with security group open to access from anywhere for port 22 and 8080
3: Instead of running the Jenkins binary directly on the EC2 (Amazon AMI Linux) instance, I preferred to run it as docker container
4: Install the docker binary and git binary using "yum install" (root user)
    yum install -y docker
    yum install -y git
    service docker start
    service docker status
5: Create docker user and add the docker user to the docker group
    

Rough Steps for CD Packaging Using Maven Plugin and Deploying into AWS API and Azure API - 
1. Creating docker-in-docker custom image using the Jenkins base image. Create the Dockerfile, build it and start the container
    docker build -t jenkins-maven-docker .
    docker run -d -p 5050:8080 -p 50000:50000 -v /var/run/docker.sock:/var/run/docker.sock jenkins-maven-docker
2. Setup the jenkins with creating admin credentials, install recommended plugins
3. Create a CI job pointing to the Jenkinsfile available in the github repo
4. Jenkinsfile should be able to following operations
    Stage 1 - Checkout the GitHub Springboot maven project
    Stage 2 - Compile, test and build the project
    Stage 3 - Take the target jar and create a Dockerfile to build an image
    Stage 4 - Push the image to dockerhub (optional step)
    Stage 5 - Start the docker container

