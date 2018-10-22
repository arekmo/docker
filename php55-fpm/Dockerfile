FROM debian:wheezy
ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update
RUN apt-get -y install wget curl git procps nano unzip

RUN wget -O- http://www.dotdeb.org/dotdeb.gpg | apt-key add -

RUN echo "deb http://packages.dotdeb.org wheezy all" > /etc/apt/sources.list.d/dotdeb.list \
     && echo "deb-src http://packages.dotdeb.org wheezy all" >> /etc/apt/sources.list.d/dotdeb.list

RUN echo "deb http://packages.dotdeb.org wheezy-php55 all" >> /etc/apt/sources.list.d/dotdeb-php55.list \
 && echo "deb-src http://packages.dotdeb.org wheezy-php55 all" >> /etc/apt/sources.list.d/dotdeb-php55.list

RUN apt-get clean && apt-get update

RUN apt-get --no-install-recommends -y install php5 php5-cli php5-fpm php5-readline php5-redis php5-curl php5-gd php5-imagick php5-intl \
	php5-mcrypt php5-memcache php5-mysqlnd php5-pgsql php5-memcached php5-mongo \
	php-pear php-log

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin/ --filename=composer

RUN apt-get -qy autoremove

CMD ["php5-fpm", "-F"]

EXPOSE 9000
