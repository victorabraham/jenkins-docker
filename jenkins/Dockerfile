FROM jenkins/jenkins:lts
LABEL maintainer=”teamgracecg@gmail.com”
# Creating folders folders as root and giving access to jenkins user
USER root
RUN apt-get update 
RUN apt-get install -y software-properties-common
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash -
RUN apt-get install -y nodejs
RUN npm i -g sfdx-cli
RUN mkdir /var/log/jenkins
RUN mkdir /var/cache/jenkins
RUN chown -R  jenkins:jenkins /var/log/jenkins
RUN chown -R  jenkins:jenkins /var/cache/jenkins
USER jenkins
# Allocating more memory if required
# ENV JAVA_OPTS="-Xmx8192m"
# ENV JENKINS_OPTS=" --handlerCountMax=300"
ENV JENKINS_OPTS=" --logfile=/var/log/jenkins/jenkins.log --webroot=/var/cache/jenkins/war"
# Use below command if you want to run the docker continer without compose
# docker run -p 8080:8080 -p 50000:50000 --name=jenkins-master --mount source=jenkins-log,target=/var/log/jenkins --mount source=jenkins-data,target=/var/jenkins_home -d myjenkins
