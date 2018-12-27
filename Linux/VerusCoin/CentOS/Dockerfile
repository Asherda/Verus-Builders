FROM centos:7
MAINTAINER Asher Dawes asher.dawes@gmail.com

RUN yum update && \
    yum install -y \
    autoconf \
    libtool \
    unzip \
    epel-release \
    git \
    python \
    python34-devel \
    make \
    wget \
    curl \
    curl-devel \
    automake \
    gcc \
    gcc-c++ \
    patch \
    which \
    glibc-static \
    libstdc++-static \
    centos-release-scl-rh && \
    yum install -y devtoolset-7 \
    devtoolset-7-binutils-devel \
    lbzip2 && \
    update-alternatives --install /usr/bin/gcc-7.3 gcc-7.3 /opt/rh/devtoolset-7/root/usr/bin/gcc 10 && \
    update-alternatives --install /usr/bin/g++-7.3 g++-7.3 /opt/rh/devtoolset-7/root/usr/bin/g++ 10 && \
    scl enable devtoolset-7 sh && \
    source /opt/rh/devtoolset-7/enable

ENV CC=/opt/rh/devtoolset-7/root/usr/bin/gcc \
    CXX=/opt/rh/devtoolset-7/root/usr/bin/g++

VOLUME /home
WORKDIR /home

