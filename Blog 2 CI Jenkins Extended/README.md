DevOps Blog 2: Continuation of previous post - Extending CI pipeline Jenkins Setup 

Project: Continuation of previous post - Extending CI pipeline Jenkins Setup 
Outcome: Learn to install the Jenkins as Docker Container in EC2 instance and setup a simple CI Pipeline.

To view the detailed post follow me at LinkedIn https://www.linkedin.com/in/mukesh-kuduva-vivekanandan/

Project: CI Jenkins Setup Using AWS EC2 Instance - Cont of Blog Post 1
Outcome: In first blog post we have created a simple jenkins pipeline and create job to run the Jenkins file to print Hello World, In this we are improving the Jenkinsfile to checkout the Java based maven project and create stages in Jenkinsfile to compile and execute a unit test.
    Reference to Post 1 - 

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
10: Create github code repo for maven project. A sample maven project can be anything of your choice. Example Spring boot API Project
11: Enhance the Jenkins file to create stage checkout the maven project from Github ,create stage to compile and create stage to run unit test
