FROM ubuntu:xenial

RUN apt-get update

# Required for CircleCI
RUN apt-get install -y \
  git \
  ssh \
  tar \
  gzip \
  ca-certificates \
  wget

# gcc
RUN apt-get install -y build-essential

# CMake 3.10
RUN cd /tmp/ && wget https://cmake.org/files/v3.10/cmake-3.10.3.tar.gz \
  && tar -xvf cmake-3.10.3.tar.gz \ 
  && cd cmake-3.10.3 \
  && ./bootstrap \
  && make \
  && make install

# Boost 1.67
RUN cd /tmp/ && wget https://dl.bintray.com/boostorg/release/1.67.0/source/boost_1_67_0.tar.gz
RUN cd /usr/local/include/ && tar -xf /tmp/boost_1_67_0.tar.gz

# Cleanup
RUN apt-get clean && rm -rf /tmp/*
