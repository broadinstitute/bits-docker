FROM ubuntu:latest as build

RUN apt-get update && apt-get install -y \
	g++ \
	cmake \
	libboost-all-dev \
	pandoc \
	zlib1g-dev \
	libbz2-dev \
	libsqlite3-dev \
	git

WORKDIR /tmp

RUN git clone https://github.com/data61/gossamer.git

WORKDIR /tmp/gossamer/build

RUN cmake .. && make && make test && make install

FROM ubuntu:latest

COPY --from=build /usr/local /usr/local

COPY --from=build /usr/lib/x86_64-linux-gnu /usr/lib/x86_64-linux-gnu
