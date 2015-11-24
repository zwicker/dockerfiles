FROM ubuntu:14.04
MAINTAINER Emmet Memery "emmet@mallpup.com"

RUN apt-get update && apt-get install -y software-properties-common

RUN add-apt-repository ppa:mc3man/trusty-media

RUN apt-get update && apt-get install -y \
    curl \
    git \
    python \
    python-dev \
    python-pip \
    cython \
	libswscale-dev \
    python-pycurl \
    python-software-properties \
    sudo \
    postgresql-client \
    ffmpeg \
	build-essential \
	libpq-dev \
    libjpeg-dev \
    libavutil-dev \
    libavcodec-dev \
    libavformat-dev \
    libpng-dev \
    libxml2-dev \
    libxslt1-dev \
    libmemcached-dev \
    nodejs \
    nodejs-legacy \
    npm

RUN npm install -g bower