FROM ubuntu:16.04
MAINTAINER Asher Dawes asher.dawes@gmail.com

RUN apt-get update && \
    apt-get -y install \
    software-properties-common \
    ca-certificates && \
    add-apt-repository ppa:ubuntu-toolchain-r/test && \
    apt-get upgrade -y && \
    apt-get update && \
    apt-get -y install \
    build-essential \
    pkg-config \
    libc6-dev \
    m4 \
    autoconf \
    curl \
    libtool \
    make \
    git \
    ncurses-dev \
    unzip \
    python \
    zlib1g-dev \
    wget \
    bsdmainutils \
    automake \
    libssl-dev \
    libprotobuf-dev \
    protobuf-compiler \
    libqrencode-dev \
    libdb++-dev \
    gcc \
    g++ \
    libgconf-2-4 && \
    apt-get -y clean; \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

VOLUME /build
WORKDIR /build


