FROM ubuntu:xenial
MAINTAINER Asher Dawes <asher.dawes@gmail.com>

ENV DEBIAN_FRONTEND=noninteractive \
    CC=/usr/bin/gcc \
    CXX=/usr/bin/g++-6

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
    cuda-8-0 \
    g++-6

VOLUME /home
WORKDIR /home


