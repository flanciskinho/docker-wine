# start from ubuntu image
FROM ubuntu:19.04

RUN apt update
## to install wget and gcc
RUN apt install -y wget build-essential
## install 32 bits dependencies for wine
RUN apt install -y lib32z1 gcc-multilib g++-multilib
#RUN apt install -y xserver-xorg-dev:i386 libfreetype6-dev:i386
 
## install dependencies for wine
RUN apt install -y flex bison

## download wine
RUN wget https://dl.winehq.org/wine/source/4.0/wine-4.0.tar.xz
RUN unxz wine-4.0.tar.xz 
RUN tar xf wine-4.0.tar
RUN cd wine-4.0 \
    && ./configure --without-freetype --without-x\
    && make -j 4 \
    && make install

RUN export LD_LIBRARY_PATH="$PREFIX/lib:$LD_LIBRARY_PATH" 

RUN echo "$PREFIX/lib" > /etc/ld.so.conf.d/wineLib.conf
RUN ldconfig


