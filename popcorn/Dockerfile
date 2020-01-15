FROM python:2.7.17-slim-buster as builder

WORKDIR /opt

RUN	apt-get -y update && \
	apt-get -y upgrade && \
	apt-get -y install git && \
	apt-get -y install gcc && \
	apt-get -y install g++ && \
	git clone https://github.com/brielin/Popcorn.git && \
	cd Popcorn && \
	pip install numpy && \
	pip install dill && \
	pip install psutil && \
	pip install -r requirements.txt  && \
	python setup.py install && \
	apt-get -y remove git && \
	apt-get -y remove gcc && \
	apt-get -y remove g++ && \
	cd /opt && \
	rm -rf Popcorn && \
	apt-get clean && \
	rm -rf /var/lib/apt/lists/*

