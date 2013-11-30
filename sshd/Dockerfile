FROM ubuntu:12.04
RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update
RUN apt-get install telnet man less vim screen openssh-server --yes
RUN apt-get upgrade --yes
RUN locale-gen en_US en_US.UTF-8

RUN mkdir /var/run/sshd
RUN echo "root\nroot" > /password 
RUN cat /password | passwd

RUN echo "" > /autoexec.sh
RUN chmod u+x /autoexec.sh
RUN sed -i '1i''/usr/sbin/sshd -D' /autoexec.sh

CMD /autoexec.sh
EXPOSE 22
