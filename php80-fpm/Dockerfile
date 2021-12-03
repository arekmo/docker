FROM phpdockerio/php80-fpm

COPY --from=composer:2.1.14 /usr/bin/composer /usr/bin/composer

RUN apt-get update \
    && apt-get -y --no-install-recommends install git ssh-client curl software-properties-common \
    php8.0-amqp php8.0-bcmath php8.0-gd php8.0-gmp php8.0-imagick php8.0-memcached \
    php8.0-mysql php8.0-pgsql php8.0-soap php8.0-xdebug php8.0-xhprof php8.0-mongodb \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*
