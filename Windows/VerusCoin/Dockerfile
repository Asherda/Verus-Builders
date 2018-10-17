FROM ubuntu:bionic
MAINTAINER Asher Dawes asher.dawes@gmail.com

ENV PATH=/root/.cargo/bin:$PATH

RUN apt-get update && apt-get -y install \
  autoconf \
  automake \
  autogen \
  bsdmainutils \
  cmake \
  curl \
  libc6-dev \
  libcap-dev \
  libcurl4-gnutls-dev \
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
  python-zmq \
  software-properties-common \
  unzip \
  wget \
  zip \
  zlib1g-dev && \
  curl https://sh.rustup.rs -sSf | \
  sh -s -- --default-toolchain stable -y && \
  rustup update && \
  rustup target add x86_64-pc-windows-gnu && \
  apt-get -y autoremove; \
  apt-get -y autoclean; \
  apt-get -y clean && \
rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
