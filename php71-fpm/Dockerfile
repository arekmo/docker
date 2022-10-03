FROM php:7.1-fpm-alpine

RUN apk update && apk add curl git wget

RUN curl -sSLf \
        -o /usr/local/bin/install-php-extensions \
        https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions && \
    chmod +x /usr/local/bin/install-php-extensions && \
    install-php-extensions amqp apcu bcmath gmp gd imagick memcached mongodb mysqli pdo_mysql pdo_pgsql soap zip xdebug xhprof

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin/ --filename=composer --version=2.2.18
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin/ --filename=composer1 --version=1.10.26

EXPOSE 9000
