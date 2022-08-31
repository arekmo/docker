FROM phpdockerio/php71-fpm

RUN apt-get update && apt search php7 \
    && apt-get -y --no-install-recommends install git ssh-client curl software-properties-common \
    php7.1-amqp php7.1-bcmath php7.1-gd php7.1-gmp php7.1-imagick php7.1-memcached \
    php7.1-mysql php7.1-pgsql php7.1-soap php7.1-xdebug php7.1-xhprof php7.1-mongodb \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin/ --filename=composer --version=2.4.1
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin/ --filename=composer1 --version=1.10.23
