FROM php:8.3-fpm-alpine

RUN set -ex \
    && apk --no-cache add \
    postgresql-dev

RUN docker-php-ext-install pdo_pgsql opcache 

RUN apk update \
    && apk add --no-cache $PHPIZE_DEPS linux-headers

RUN pecl install xdebug \
    && docker-php-ext-enable xdebug

RUN apk del $PHPIZE_DEPS \
    && rm -rf /tmp/pear