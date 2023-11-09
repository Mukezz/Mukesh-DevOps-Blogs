# Use the official Jenkins image as a base image
FROM jenkins/jenkins:lts

# Install necessary packages
USER root
RUN apt-get update && \
    apt-get install -y apt-transport-https \
                       ca-certificates \
                       curl \
                       gnupg-agent \
                       software-properties-common && \
    rm -rf /var/lib/apt/lists/*

# Install Docker CLI
RUN curl -fsSL https://download.docker.com/linux/debian/gpg | apt-key add - && \
    add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian $(lsb_release -cs) stable" && \
    apt-get update && \
    apt-get install -y docker-ce-cli && \
    rm -rf /var/lib/apt/lists/*

# Install Maven
RUN apt-get install -y maven

# Set the environment variable for Maven
ENV MAVEN_HOME /usr/share/maven
ENV PATH $MAVEN_HOME/bin:$PATH
