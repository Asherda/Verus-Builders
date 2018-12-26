FROM centos:7
MAINTAINER Asher Dawes asher.dawes@gmail.com
ENV CXX=/opt/rh/devtoolset-8/root/usr/bin/g++ \
    CC=/opt/rh/devtoolset-8/root/usr/bin/gcc

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
    wget -r -l1 -H -t1 -nd -N -np  https://cbs.centos.org/repos/sclo7-devtoolset-8-rh-candidate/x86_64/os/Packages && \
    yum install -y lbzip2 *.rpm && \
    update-alternatives --install /usr/bin/gcc-8.2 gcc-8.2 /opt/rh/devtoolset-8/root/usr/bin/gcc 10 && \
    update-alternatives --install /usr/bin/g++-8.2 g++-8.2 /opt/rh/devtoolset-8/root/usr/bin/g++ 10 && \
    scl enable devtoolset-8 sh && \
    source /opt/rh/devtoolset-8/enable && \
    yum clean all

VOLUME /home
WORKDIR /home

