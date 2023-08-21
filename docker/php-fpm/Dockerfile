FROM php:8.1-fpm

RUN apt-get update && apt-get install -y wget git unzip libxml2-dev libpng-dev zlib1g-dev alien libaio1 \
    && pecl install xdebug-3.2.0 \
    && apt-get install -y --no-install-recommends libpq-dev \
    && docker-php-ext-enable xdebug \
    && docker-php-ext-install pdo pdo_pgsql

RUN wget https://getcomposer.org/installer -O - -q \
    | php -- --install-dir=/bin --filename=composer --quiet

ENV COMPOSER_ALLOW_SUPERUSER 1

WORKDIR /var/www
