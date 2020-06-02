FROM ubuntu:xenial
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
    gcc-6 \
    g++-6 \
    libgconf-2-4 && \
    apt-get -y clean; \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
    RUN update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-6 60 \
    --slave /usr/bin/g++ g++ /usr/bin/g++-6 \
    --slave /usr/bin/gcc-ar gcc-ar /usr/bin/gcc-ar-6 \
    --slave /usr/bin/gcc-nm gcc-nm /usr/bin/gcc-nm-6 \
    --slave /usr/bin/gcc-ranlib gcc-ranlib /usr/bin/gcc-ranlib-6 && \
    update-alternatives --config gcc

VOLUME /build
WORKDIR /build

