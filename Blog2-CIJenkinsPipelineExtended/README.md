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
4: Install the docker binary and git binary using "yum install"
5: Login as root user. Create dockerfile to create an image with jenkins and maven in order to compile the Java based maven project in jenkins. Name the custom image as jenkins-maven. Show the docker run command for jenkins-maven custom docker image
6: Complete the jenkins setup by using the initial admin password , create admin user and install the recommended plugin
7: Create a github repo for maven project using springboot initializer with Java 11 / Spring 2.7.15 and create /hello get endpoint to print Hello World json response. create unit test case for the /hello endpoint
8: Create a github repository with Jenkinsfile to create stages for checkout the maven project from Github ,create stage to clean compile and create stage to run unit test. Jenkinsfile should use the Maven_3_8_7 as tools
9: Create jenkins job pipeline pointing to github repository Jenkinsfile. Use github-credentials as username and personnal access tokens / fine-grained tokens to access the 2 github repository that was created in step 8.
