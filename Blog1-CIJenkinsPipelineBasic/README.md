DevOps Blog 1: CI Jenkins Setup Using AWS EC2 Instance

Project: CI Jenkins Setup Using AWS EC2 Instance
Outcome: Learn to install the Jenkins as Docker Container in EC2 instance and setup a simple CI Pipeline.

To view the detailed post follow me at LinkedIn https://www.linkedin.com/in/mukesh-kuduva-vivekanandan/

Rough Steps for CI using Jenkins - 

1: Login into AWS console 
2: Spin up the free tier EC2 instance with security group open to access from anywhere for port 22 and 8080
3: Instead of running the Jenkins binary directly on the EC2 (Amazon AMI Linux) instance, I preferred to run it as docker container
4: Install the docker binary using the "yum install docker"
5: Refer to the jenkins docker hub page to dowload the docker image & run the container service
6: Complete the jenkins setup by using the initial admin password , create admin user and install the recommended plugin
7: Install the git binary on the server using yum
8: Create a github repository with sample Jenkinsfile with hello world
9: Create jenkins job pipeline pointing to github repository Jenkinsfile
10: Execute the jenkins job
