FROM phpdockerio/php71-fpm

COPY --from=composer:2.1.14 /usr/bin/composer /usr/bin/composer
COPY --from=composer:1.10.23 /usr/bin/composer /usr/bin/composer1

RUN apt-get update \
    && apt-get -y --no-install-recommends install git ssh-client curl software-properties-common \
    php7.1-amqp php7.1-bcmath php7.1-gd php7.1-gmp php7.1-imagick php7.1-memcached \
    php7.1-mysql php7.1-pgsql php7.1-soap php7.1-xdebug php7.1-xhprof php7.1-mongodb \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*
