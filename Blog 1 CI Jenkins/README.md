Rough Steps for CI using Jenkins - 

1: Login into AWS console 
2: Spin up the free tier EC2 instance with security group open to access from anywhere for port 22 and 8080
3: Instead of running the Jenkins binary directly on the EC2 (Amazon AMI Linux) instance, I preferred to run it as docker container
4: Install the docker binary using the "yum install docker"
5: Refer to the jenkins docker hub page to dowload the docker image & run the container service

Refined and Elobrated steps using ChatGPT 3.5