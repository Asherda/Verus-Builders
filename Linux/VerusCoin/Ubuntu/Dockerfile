FROM ubuntu:bionic
MAINTAINER Asher Dawes asher.dawes@gmail.com

RUN apt-get update && \
    apt-get upgrade -y && \
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
    gcc-8 \
    g++-8 \
    libcurl4-openssl-dev \
    libgconf-2-4 && \
    apt-get -y clean; \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
    RUN update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-8 80 \
    --slave /usr/bin/g++ g++ /usr/bin/g++-8 \
    --slave /usr/bin/gcc-ar gcc-ar /usr/bin/gcc-ar-8 \
    --slave /usr/bin/gcc-nm gcc-nm /usr/bin/gcc-nm-8 \
    --slave /usr/bin/gcc-ranlib gcc-ranlib /usr/bin/gcc-ranlib-8 && \
    update-alternatives --config gcc

VOLUME /build
WORKDIR /build

