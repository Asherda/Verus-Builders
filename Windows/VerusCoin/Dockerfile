FROM ubuntu:focal
MAINTAINER Asher Dawes asher.dawes@gmail.com

RUN apt-get update && apt-get upgrade -y && apt-get -y install \
  autoconf \
  automake \
  autogen \
  bsdmainutils \
  cmake \
  curl \
  git \
  libc6-dev \
  libcap-dev \
  libdb++-dev \
  libqrencode-dev \
  libprotobuf-dev \
  libssl-dev \
  libtool \
  libz-dev \
  libbz2-dev \
  m4 \
  make \
  mingw-w64\
  ncurses-dev \
  pkg-config \
  protobuf-compiler \
  python \
  unzip \
  wget \
  zip \
  zlib1g-dev && \
  apt-get -y autoremove; \
  apt-get -y autoclean; \
  apt-get -y clean && \
  rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

VOLUME /build
WORKDIR /build
