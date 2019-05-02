# use ubuntu image
# source https://hub.docker.com/_/ubuntu
FROM ubuntu:19.04

# enable 32 bit architecture
RUN dpkg --add-architecture i386


# update system
# install wget and wine dependencies
RUN apt-get update && apt-get install -y wget gnupg software-properties-common

# add repository key and install (wine)
RUN wget -qO - https://dl.winehq.org/wine-builds/winehq.key | apt-key add -
RUN apt-add-repository 'deb https://dl.winehq.org/wine-builds/ubuntu/ disco main'
RUN apt-get update && apt-get install -y --install-recommends wine

RUN echo "Installed wine version: `wine --version`"


