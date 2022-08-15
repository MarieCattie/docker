FROM php:7.0-apache
 
# PHP extensions
RUN apt-get update && apt-get install -y \
        libmcrypt-dev \
        zlib1g-dev \
        curl \
        libjpeg62-turbo-dev \
        libfreetype6-dev \
        libpng-dev \
        libmcrypt-dev \
    && docker-php-ext-install -j$(nproc) iconv mcrypt mbstring iconv mysqli pdo_mysql zip opcache \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd
 
# Apache modules
RUN a2enmod rewrite