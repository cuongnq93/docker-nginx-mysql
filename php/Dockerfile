FROM php:7.2-fpm

RUN apt-get update && \
    apt-get install -y --no-install-recommends git zip unzip

RUN  curl -sS https://getcomposer.org/installer | php && mv composer.phar /usr/local/bin/composer