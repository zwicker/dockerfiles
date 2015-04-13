# OS declaration
FROM ubuntu:14.04

# Maintainer declaration
MAINTAINER Emmet Memery <emmet@shorthand.com>

# Fix upstart (see https://github.com/dotcloud/docker/issues/1024)
# RUN dpkg-divert --local --rename --add /sbin/initctl
# RUN ln -s /bin/true /sbin/initctl

# Build dependencies
# RUN echo 'deb http://archive.ubuntu.com/ubuntu precise main universe' > /etc/apt/sources.list.d/ubuntu-precise.list
# RUN echo 'deb http://downloads-distro.mongodb.org/repo/ubuntu-upstart dist 10gen' > /etc/apt/sources.list.d/mongodb.list
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB10
RUN apt-get -y update
RUN apt-get install -y -q curl make build-essential zlib1g-dev libssl-dev libreadline6-dev libyaml-dev nginx supervisor git
# RUN gem install bundler

# Install NodeJS
RUN curl -L http://nodejs.org/dist/v0.12.2/node-v0.12.2.tar.gz | tar -xz
RUN cd /node-v0.12.2 && ./configure
RUN cd /node-v0.12.2 && make && make install && make clean

# Global NPM installs
RUN npm install --silent -g grunt-cli bower protractor sails

# Add SSH keys
#ADD .ssh /user/deploy/.ssh

# # Build src
# RUN git clone git@github.com:group/project.git /project
# RUN cd /project && bundle install
# RUN cd /project && npm install --silent
# RUN cd /project && bower --allow-root install
# RUN cd /project && grunt build
#
# # Nginx config
# RUN rm /etc/nginx/sites-enabled/*
# RUN cp -r /project/deploy/nginx/* /etc/nginx/
#
# # Supervisor
# RUN mkdir -p /var/log/supervisor
# RUN cp -r /project/deploy/supervisord/* /etc/supervisor/
