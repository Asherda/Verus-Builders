FROM ubuntu:bionic
MAINTAINER Asher Dawes asher.dawes@gmail.com

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get -y install \
    build-essential \
    pkg-config \
    libc6-dev \
    libc6-dev-arm64-cross \
    m4 \
    autoconf \
    curl \
    libtool \
    make \
    git \
    gcc-aarch64-linux-gnu \
    g++-aarch64-linux-gnu \
    binutils-aarch64-linux-gnu \
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
    libgconf-2-4 \
    g++-multilib && \
    apt-get -y clean; \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

VOLUME /build
WORKDIR /build
