FROM ubuntu:xenial
MAINTAINER Asher Dawes <asher.dawes@gmail.com>

ENV DEBIAN_FRONTEND=noninteractive \
    CC=/usr/bin/gcc-7 \
    CXX=/usr/bin/g++-7 \
    PATH=$PATH:/usr/local/cuda/bin


RUN apt-get update && apt-get install -y \
    apt-utils \
    build-essential \
    software-properties-common \
    libcurl4-gnutls-dev \
    libssl-dev \
    libjansson-dev \
    gcc \
    automake \
    autotools-dev \
    wget && \
    add-apt-repository ppa:ubuntu-toolchain-r/test -y && \
    wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/cuda-repo-ubuntu1604_8.0.61-1_amd64.deb && \
    dpkg -i cuda-repo-ubuntu1604_8.0.61-1_amd64.deb && \
    apt-get update && apt-get install -y \
    gcc-7 \
    g++-7 \
    cuda

VOLUME /home
WORKDIR /home


