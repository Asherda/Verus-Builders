FROM centos:8
MAINTAINER Asher Dawes asher.dawes@gmail.com

RUN yum update -y && \
    yum install -y \
    autoconf \
    libtool \
    unzip \
    epel-release \
    git \
    make \
    wget \
    automake \
    gcc \
    gcc-c++ \
    patch \
    which \
    lbzip2 && \
    dnf --enablerepo=PowerTools install glibc-static libstdc++-static

VOLUME /build
WORKDIR /build

