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

# gcc + cmake
RUN apt-get install -y build-essential cmake

# Boost 1.67
RUN cd /tmp && wget https://dl.bintray.com/boostorg/release/1.67.0/source/boost_1_67_0.tar.gz
RUN cd /usr/local/include && tar -xf /tmp/boost_1_67_0.tar.gz

# Cleanup
RUN apt-get clean && rm -rf /tmp/*