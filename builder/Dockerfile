FROM ubuntu:20.04
RUN apt update
ENV TZ=Europe/Moscow
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

#Install maven
RUN apt Install maven -y
ENV PATH=$PATH:/usr/bin

#Install Docker
RUN apt Install docker.io -y

# Clear cache
RUN apt-get clean