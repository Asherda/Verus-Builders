FROM ubuntu:xenial
MAINTAINER Asher Dawes <asher.dawes@gmail.com>

ENV DEBIAN_FRONTEND=noninteractive \
    CC=/usr/bin/gcc-6 \
    CXX=/usr/bin/g++-6 \
    PATH=$PATH:/usr/local/cuda/bin


RUN apt-get update && apt-get install -y \
    apt-utils \
    build-essential \
    curl \
    software-properties-common \
    libcurl4-gnutls-dev \
    libssl-dev \
    libjansson-dev \
    automake \
    autotools-dev \
    wget && \
    add-apt-repository ppa:ubuntu-toolchain-r/test -y && \
    wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/cuda-repo-ubuntu1604_8.0.61-1_amd64.deb && \
    dpkg -i cuda-repo-ubuntu1604_8.0.61-1_amd64.deb && \
    apt-get update && apt-get install -y \
    gcc-6 \
    g++-6 \
    cuda-9-0 && \
    apt-get -y autoremove; \
    apt-get -y autoclean; \
    apt-get -y clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

VOLUME /build
WORKDIR /build


