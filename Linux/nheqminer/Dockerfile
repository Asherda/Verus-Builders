FROM ubuntu:xenial
MAINTAINER Asher Dawes <asher.dawes@gmail.com>

ENV BOOST_MAJOR_VERSION=1 \
    BOOST_MINOR_VERSION=72 \
    BOOST_PATCH=0 \
    BOOST_ROOT=/usr/include/boost \
    PATH=:${PATH}:/CMake/bin


ENV BOOST_VERSION=${BOOST_MAJOR_VERSION}.${BOOST_MINOR_VERSION}.${BOOST_PATCH} \
    BOOST_VERSION_=${BOOST_MAJOR_VERSION}.${BOOST_MINOR_VERSION}_ \
    BOOST_TAR=boost_${BOOST_MAJOR_VERSION}_${BOOST_MINOR_VERSION}_${BOOST_PATCH}.tar.gz

ENV BOOST_DOWNLOAD_URL=https://sourceforge.net/projects/boost/files/boost/${BOOST_VERSION}/${BOOST_TAR} 

RUN apt-get update  && \
    apt-get upgrade -y \
    apt-get install -y \
    autoconf \
    libtool \
    unzip \
    git \
    make \
    python \
    wget \
    curl  \
    automake \
    gcc \
    g++ \
    cmake \
    git clone https://github.com/Kitware/CMake.git && \
    cd CMake && \
    ./bootstrap && make && make install && \
    cd .. && \
    wget --max-redirect 3 ${BOOST_DOWNLOAD_URL} && \
    mkdir -p /usr/include/ && \
    tar -zxf ${BOOST_TAR} && \
    rm ${BOOST_TAR} && \
    cd boost_${BOOST_MAJOR_VERSION}_${BOOST_MINOR_VERSION}_${BOOST_PATCH} && \
    ./bootstrap.sh --prefix=${BOOST_ROOT} --libdir=${BOOST_ROOT}/lib  && \
    ./b2 --with-system  \
        --with-filesystem  \
        --with-log_setup \
        --with-log  \
        --with-date_time \
        --with-thread \
        --libdir=${BOOST_ROOT}/lib \
        address-model=64 \
         -j$(nproc) \
        link=static \
        threading=multi \
        cxxflags="-march=x86-64 -std=c++11" && \
    ./b2 install -j$(nproc) && \
    cd .. && \
    rm -rf boost_${BOOST_MAJOR_VERSION}_${BOOST_MINOR_VERSION}_${BOOST_PATCH}

VOLUME /build
WORKDIR /build


