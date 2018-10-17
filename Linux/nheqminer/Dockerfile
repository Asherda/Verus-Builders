FROM debian:jessie-slim
MAINTAINER Asher Dawes <asher.dawes@gmail.com>

ENV DEBIAN_FRONTEND=noninteractive \
    BOOST_MAJOR_VERSION=1 \
    BOOST_MINOR_VERSION=67\
    BOOST_PATCH=0 \
    BOOST_ROOT=/usr/include/boost


ENV BOOST_VERSION=${BOOST_MAJOR_VERSION}.${BOOST_MINOR_VERSION}.${BOOST_PATCH} \
    BOOST_VERSION_=${BOOST_MAJOR_VERSION}.${BOOST_MINOR_VERSION}_ \
    BOOST_TAR=boost_${BOOST_MAJOR_VERSION}_${BOOST_MINOR_VERSION}_${BOOST_PATCH}.tar.gz

ENV BOOST_DOWNLOAD_URL=https://sourceforge.net/projects/boost/files/boost/${BOOST_VERSION}/${BOOST_TAR} 

RUN apt-get -qq update && apt-get install -q -y \
    cmake && \
    apt-get -qq update && \
    apt-get install -y \
    g++-multilib \
    curl \
    wget && \
    wget --max-redirect 3 ${BOOST_DOWNLOAD_URL} && \
    mkdir -p /usr/include/ && \
    tar -zxf ${BOOST_TAR} && \
    rm ${BOOST_TAR} && \
    mkdir ${BOOST_ROOT} && \
    cd boost_${BOOST_MAJOR_VERSION}_${BOOST_MINOR_VERSION}_${BOOST_PATCH} && \
    ./bootstrap.sh --prefix=${BOOST_ROOT} --libdir=${BOOST_ROOT}/lib  && \
    ./b2 --libdir=${BOOST_ROOT}/lib \
    address-model=64 \
    -j$(nproc) \
    link=static \
    threading=multi \
    cxxflags="-march=x86-64 -std=c++11" && \
    ./b2 install -j$(nproc) && \
    cd .. && \
    rm -rf boost_${BOOST_MAJOR_VERSION}_${BOOST_MINOR_VERSION}_${BOOST_PATCH} && \
    apt-get -y clean; \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
