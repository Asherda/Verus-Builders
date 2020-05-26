FROM centos:7
MAINTAINER Asher Dawes asher.dawes@gmail.com

RUN yum update -y && \
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
    automake \
    gcc \
    gcc-c++ \
    patch \
    which \
    glibc-static \
    libstdc++-static \
    centos-release-scl && \
    yum install -y devtoolset-8 \
    devtoolset-8-binutils-devel \
    lbzip2 && \
    scl enable devtoolset-8 sh && \
    scl enable devtoolset-8 bash && \
    source /opt/rh/devtoolset-8/enable

VOLUME /build
WORKDIR /build

