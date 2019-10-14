FROM php:7-fpm

RUN apt-get update && apt-get install -y --no-install-recommends apt-utils

# PHP extensions
RUN apt-get update && apt-get install -y \
		libfreetype6-dev \
 		libjpeg62-turbo-dev \
 		libmcrypt-dev \
 		libpng-dev \
  && pecl install mcrypt-1.0.2 \
	&& docker-php-ext-install -j$(nproc) mbstring pdo_mysql tokenizer iconv mysqli \
	&& docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
	&& docker-php-ext-install -j$(nproc) gd
