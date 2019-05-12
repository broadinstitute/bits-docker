FROM centos:7 as builder

RUN yum -y install epel-release && \
  yum -y update && \
  yum -y install unzip \
  make \
  cmake3 \
  gcc \
  gcc-c++ \
  zlib-devel && \
  yum -y clean all && \
  cd /tmp && \
  curl -LOk https://github.com/statgen/METAL/archive/2017-12-21.zip && \
  unzip 2017-12-21.zip && \
  cd /tmp/METAL-2017-12-21 && \
  mkdir build && \
  cd build && \
  cmake3 .. && \
  make && \
  make test && \
  make install && \
  cd /usr/local/bin && \
  cp /tmp/METAL-2017-12-21/build/bin/metal . && \
  rm -rf /tmp/METAL-2017-12-21 

FROM centos:7

WORKDIR /usr/local/bin
COPY --from=builder /usr/local/bin .
