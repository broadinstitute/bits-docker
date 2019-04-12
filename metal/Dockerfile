FROM centos:7

RUN yum -y install epel-release && yum -y update && yum -y install unzip && yum -y install make &&  yum -y install cmake3 && yum -y install gcc && yum -y install gcc-c++ && yum -y install zlib-devel && cd /tmp && curl -LOk https://github.com/statgen/METAL/archive/2017-12-21.zip && unzip 2017-12-21.zip && cd /tmp/METAL-2017-12-21 && mkdir build && cd build && cmake3 .. && make && make test && make install && cd /usr/local/bin && cp /tmp/METAL-2017-12-21/build/bin/metal . && rm -rf /tmp/METAL-2017-12-21
