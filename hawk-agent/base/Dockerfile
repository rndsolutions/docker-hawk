FROM ubuntu:14.04.4
MAINTAINER Radoslav Minchev <rminchev@rnd-solutions.net>

#install java 8
RUN apt-get update \ 
    && apt-get install software-properties-common -y \
    && add-apt-repository ppa:webupd8team/java -y

RUN apt-get update \
    && echo debconf shared/accepted-oracle-license-v1-1 select true | debconf-set-selections \
    && echo debconf shared/accepted-oracle-license-v1-1 seen true | sudo debconf-set-selections
    
RUN apt-get install oracle-java8-installer -y
    
    #&& apt-get install oracle-java8-set-default
   
#install gradle
RUN add-apt-repository ppa:cwchien/gradle \
    && apt-get update \
    && apt-get install gradle -y
   