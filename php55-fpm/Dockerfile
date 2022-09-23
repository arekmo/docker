FROM php:5.5-fpm

RUN apt-get update && apt-get install -y --no-install-recommends curl git wget

RUN curl -sSLf \
        -o /usr/local/bin/install-php-extensions \
        https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions && \
    chmod +x /usr/local/bin/install-php-extensions && \
    install-php-extensions amqp apcu bcmath gmp gd imagick memcached mongodb mysqli pdo_mysql pdo_pgsql soap zip xdebug xhprof

RUN install-php-extensions @fix_letsencrypt @composer-1 && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

EXPOSE 9000
