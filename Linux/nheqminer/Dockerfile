FROM centos:7
MAINTAINER Asher Dawes <asher.dawes@gmail.com>

ENV DEBIAN_FRONTEND=noninteractive \
    BOOST_MAJOR_VERSION=1 \
    BOOST_MINOR_VERSION=69 \
    BOOST_PATCH=0 \
    BOOST_ROOT=/usr/include/boost \
    PATH=:${PATH}:/CMake/bin


ENV BOOST_VERSION=${BOOST_MAJOR_VERSION}.${BOOST_MINOR_VERSION}.${BOOST_PATCH} \
    BOOST_VERSION_=${BOOST_MAJOR_VERSION}.${BOOST_MINOR_VERSION}_ \
    BOOST_TAR=boost_${BOOST_MAJOR_VERSION}_${BOOST_MINOR_VERSION}_${BOOST_PATCH}.tar.gz

ENV BOOST_DOWNLOAD_URL=https://sourceforge.net/projects/boost/files/boost/${BOOST_VERSION}/${BOOST_TAR} 

RUN yum update && \
    yum install -y \
    epel-release \
    autoconf \
    libtool \
    unzip \
    git \
    make \
    python \
    python-devel \
    wget \
    curl  \
    automake \
    gcc \
    gcc-c++ \
    patch \
    which \
    glibc-static \
    libstdc++-static  \
    centos-release-scl-rh  && \
    yum install -y  \
    devtoolset-7 && \
    update-alternatives --install /usr/bin/gcc-7.3 gcc-7.3 /opt/rh/devtoolset-7/root/usr/bin/gcc 10 && \
    update-alternatives --install /usr/bin/g++-7.3 g++-7.3 /opt/rh/devtoolset-7/root/usr/bin/g++ 10 && \
    scl enable devtoolset-7 bash && \
    git clone https://github.com/Kitware/CMake.git && \
    cd CMake && \
    ./bootstrap && make && make install && \
    cd .. && \
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
    rm -rf boost_${BOOST_MAJOR_VERSION}_${BOOST_MINOR_VERSION}_${BOOST_PATCH}

VOLUME /home
WORKDIR /home
ENTRYPOINT ["/bin/bash"]


