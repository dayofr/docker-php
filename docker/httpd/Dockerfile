FROM php:7.1.6-apache

ENV APCU_VERSION 5.1.8

RUN apt-get update && apt-get install -y \
    libjpeg-dev \
    libpng12-dev \
    vim \
    git \
    libicu-dev
    
RUN a2enmod ssl rewrite
    
RUN docker-php-ext-install gd mysqli opcache pdo_mysql zip intl; 

RUN pecl install apcu-${APCU_VERSION} xdebug;
RUN docker-php-ext-enable apcu xdebug;

COPY php.ini /usr/local/etc/php/

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php composer-setup.php
RUN php -r "unlink('composer-setup.php');"
RUN mv composer.phar /usr/local/bin/composer

VOLUME /var/www/html