FROM debian:jessie

MAINTAINER Emmet Memery <emmet@mallpup.com>

ADD docker-run.sh /docker-run.sh
RUN apt-get update -q && \
apt-get install apache2 wget curl -yq && \
	echo "deb http://packages.dotdeb.org jessie all" >> /etc/apt/sources.list && \
	echo "deb-src http://packages.dotdeb.org jessie all" >> /etc/apt/sources.list && \
	wget http://www.dotdeb.org/dotdeb.gpg && \	
	apt-key add dotdeb.gpg && \
	apt-get update -q && \
	apt-get install -yq git php5 php5-mhash php5-mcrypt php5-curl php5-cli php5-mysql php5-xmlrpc php5-gd php5-cli libapache2-mod-wsgi libapache2-mod-php5 && \
	sed -i "s/variables_order.*/variables_order = \"EGPCS\"/g" /etc/php5/apache2/php.ini && \
	curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer && \
