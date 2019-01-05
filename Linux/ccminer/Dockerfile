FROM ubuntu:xenial
MAINTAINER Asher Dawes <asher.dawes@gmail.com>

RUN apt-get update && apt-get install -y \
    libcurl4-gnutls-dev \
    libssl-dev \
    libjansson-dev \
    g++ \
    gcc \
    automake \
    autotools-dev \
    build-essential \
    wget && \
    wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/cuda-repo-ubuntu1604_8.0.61-1_amd64.deb && \
    dpkg -i cuda-repo-ubuntu1604_8.0.61-1_amd64.deb && \
    apt-get update && apt-get install -y cuda-8-0

VOLUME /home
WORKDIR /home


