FROM php:7.4-fpm-alpine

COPY --from=composer /usr/bin/composer /usr/bin/composer
COPY ./docker/php/php.ini /usr/local/etc/php/

RUN apk update
RUN apk add git \
    autoconf \
    gcc \
    g++ \
    make \
    --update npm \
    && docker-php-ext-install pdo_mysql

RUN pecl install xdebug
RUN docker-php-ext-enable xdebug

WORKDIR /var/www/html