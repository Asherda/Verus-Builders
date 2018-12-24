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
    yum install -y centos-release-scl-rh \
    yum install -y devtoolset-7 && \
    update-alternatives --install /usr/bin/gcc-7.3 gcc-7.3 /opt/rh/devtoolset-7/root/usr/bin/gcc 10 && \
    update-alternatives --install /usr/bin/g++-7.3 g++-7.3 /opt/rh/devtoolset-7/root/usr/bin/g++ 10 && \
    scl enable devtoolset-7 bash && \
    wget https://dl.fedoraproject.org/pub/epel/7/x86_64/Packages/e/epel-release-7-11.noarch.rpm && \
    rpm -Uvh epel-release*rpm && \
    yum install -y lbzip2

VOLUME /home
WORKDIR /home

