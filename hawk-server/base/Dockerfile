FROM ubuntu:14.04.4
MAINTAINER Radoslav Minchev <rminchev@rnd-solutions.net>

#install git
RUN  apt-get update \
   &&  apt-get install git -y


#install - curl,  nodejs & bower
RUN sudo apt-get install curl -y \
        && curl -sL https://deb.nodesource.com/setup_5.x | sudo -E bash - \
        && sudo apt-get install -y nodejs \
	&& npm install --global bower
 
#install mono
RUN apt-get update \
	&& apt-get install -y curl \
	&& rm -rf /var/lib/apt/lists/*

RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF

RUN echo "deb http://download.mono-project.com/repo/debian wheezy/snapshots/4.2.3.4 main" > /etc/apt/sources.list.d/mono-xamarin.list \
	&& apt-get update \
	&& apt-get install -y mono-devel ca-certificates-mono fsharp mono-vbnc nuget \
	&& rm -rf /var/lib/apt/lists/*
