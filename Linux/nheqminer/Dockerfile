FROM ubuntu:xenial
MAINTAINER Asher Dawes <asher.dawes@gmail.com>

RUN apt-get update  && \
    apt-get upgrade -y && \
    apt-get install -y \
    gcc \
    g++ \
    make \
    cmake \
    libboost-all-dev && \
    apt-get -y clean; \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

VOLUME /build
WORKDIR /build


