FROM jenkins/jenkins:lts

# installing additional software to jenkins image. Changing user to root for these purposes
USER root
RUN apt-get update && apt-get install -y maven make vim nano docker docker-compose gradle git wget
# drop back to the regular jenkins user

# installing jenkins plugins from file
COPY plugins.txt /usr/share/jenkins/ref/plugins.txt
RUN /usr/local/bin/install-plugins.sh < /usr/share/jenkins/ref/plugins.txt
#
COPY executors.groovy /usr/share/jenkins/ref/init.groovy.d/executors.groovy