ARG PHP_VERSION

FROM php:${PHP_VERSION}-fpm

RUN apt-get update \
    && apt-get -y --no-install-recommends install \
    php${PHP_VERSION}-memcached \
    php${PHP_VERSION}-memcache \
    php${PHP_VERSION}-mbstring \
    php${PHP_VERSION}-mysql \
    php${PHP_VERSION}-intl \
    php${PHP_VERSION}-xdebug \
    php${PHP_VERSION}-interbase \
    php${PHP_VERSION}-soap \
    php${PHP_VERSION}-gd \
    php${PHP_VERSION}-imagick \
    php${PHP_VERSION}-opcache \
    php${PHP_VERSION}-zip \
    php-pear php-dev libmcrypt-dev gcc make autoconf libc-dev pkg-config \
    && pecl install mcrypt-1.0.3 \
    && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

RUN docker-php-ext-install mysqli && docker-php-ext-enable mysqli

WORKDIR /var/www/

RUN usermod -u 1000 www-data
