FROM ubuntu
MAINTAINER Andrey Popp <8mayday@gmail.com>

RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update
RUN apt-get install -y curl git wget make build-essential unzip openjdk-7-jre-headless

# install JDK ignoring dependency on non-hedless JRE
RUN apt-get --no-install-recommends -d -y install openjdk-7-jdk
RUN dpkg -i --ignore-depends=openjdk-7-jre /var/cache/apt/archives/openjdk-7-jdk*.deb

RUN wget http://downloads.typesafe.com/play/2.2.0/play-2.2.0.zip
RUN unzip play-2.2.0.zip
RUN rm play-2.2.0.zip
RUN mv play-2.2.0 /opt/play

ADD build.mk /
RUN curl https://github.com/hecticjeff/shoreman/raw/master/shoreman.sh -sLo /usr/local/bin/shoreman
RUN chmod +x /usr/local/bin/shoreman
