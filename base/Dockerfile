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
    libmemcached-dev 

RUN curl -sL https://deb.nodesource.com/setup_4.x | sudo -E bash - && \
    apt-get install -y nodejs

# RUN curl -L https://npmjs.org/install.sh | sh

RUN mkdir /code/ && \
    mkdir /code/reqs
RUN npm install -g npm 

ADD requirements.txt /code/
ADD reqs/common.txt /code/reqs/
ADD reqs/dev.txt /code/reqs/
ADD reqs/prod.txt /code/reqs/
ADD package.json /code/
#    nodejs \ nodejs-legacy \ npm

RUN cd /code && \
    pip install -r requirements.txt

# RUN npm install -g bower