FROM php:7.4-fpm-alpine

ENV TZ Asia/Tokyo
ENV COMPOSER_ALLOW_SUPERUSER 1

# install Lib
RUN apk update && \
  apk add --no-cache --virtual .php-builds oniguruma-dev git zip unzip

# add php-ext-module
RUN docker-php-ext-install mbstring && \
  docker-php-ext-enable mbstring

# install Composer
RUN curl -sS https://getcomposer.org/installer | php && \
  mv composer.phar /usr/local/bin/composer && \
  chmod +x /usr/local/bin/composer

WORKDIR /app