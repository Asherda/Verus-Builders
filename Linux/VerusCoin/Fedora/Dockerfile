FROM fedora
MAINTAINER Asher Dawes asher.dawes@gmail.com

RUN dnf -y update && dnf clean all
RUN dnf -y install \
     pkgconfig \
     automake \
     autoconf \
     make \
     bzip2 \
     curl \
     curl-devel \
     ncurses-devel \
     python \
     python-zmq \
     wget \
     gtest-devel \
     gcc \
     gcc-c++ \
     libtool \
     patch && \
     dnf clean all

