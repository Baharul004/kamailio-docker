FROM ubuntu
#FROM debian:jessie

#MAINTAINER Victor Seva <linuxmaniac@torreviejawireless.org>

# Important! Update this no-op ENV variable when this Dockerfile
# is updated with the current date. It will force refresh of all
# of the base images and things like 'apt-get update' won't be using
# old cached versions when the Dockerfile is built.
#ENV REFRESHED_AT 2019-05-23

ARG host_address


RUN apt-get update && \
    apt-get -y upgrade && \
    apt-get install -y nano && \
    apt-get install -y systemd && \
#    apt-get install -y net-tool && \
    apt-get install -y iproute2 && \
#    apt-get install -y  apt-utils && \
#    apt install -y  mysql-server && \
    apt-get install -y kamailio kamailio-mysql-modules

VOLUME /etc/kamailio

# clean
#RUN apt-get clean && rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["kamailio", "-DD", "-E"]
