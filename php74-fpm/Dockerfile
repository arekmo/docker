FROM phpdockerio/php74-fpm

RUN apt-get update \
    && apt-get -y --no-install-recommends install git ssh-client curl software-properties-common \
    php7.4-amqp php7.4-bcmath php7.4-gd php7.4-gmp php7.4-imagick php7.4-memcached \
    php7.4-mysql php7.4-pgsql php7.4-soap php7.4-xdebug php7.4-xhprof php7.4-mongodb \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin/ --filename=composer --version=2.4.2 && \
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin/ --filename=composer1 --version=1.10.26
