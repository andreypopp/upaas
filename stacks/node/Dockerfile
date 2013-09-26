FROM ubuntu
MAINTAINER Andrey Popp <8mayday@gmail.com>

RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update
RUN apt-get -f install -y git wget curl make build-essential python-software-properties
RUN add-apt-repository ppa:chris-lea/node.js
RUN apt-get update
RUN apt-get install -y nodejs

RUN curl https://github.com/hecticjeff/shoreman/raw/master/shoreman.sh -sLo /usr/local/bin/shoreman
RUN chmod +x /usr/local/bin/shoreman
ADD build.mk /
