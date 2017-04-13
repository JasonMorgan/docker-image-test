FROM ubuntu
RUN apt-get update
RUN apt-get install openssh-server -y
RUN mkdir /var/run/sshd
RUN apt-get install openjdk-8-jdk -y
RUN useradd --create-home --shell /bin/bash jenkins
RUN echo 'jenkins:jenkins' | chpasswd
RUN /usr/sbin/sshd
EXPOSE 22
