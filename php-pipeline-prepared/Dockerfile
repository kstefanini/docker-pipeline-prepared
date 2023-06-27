FROM php:8.2-fpm

# Installation des librairies pour les extensions PHP
RUN sed -i 's/deb\.debian\.org/ftp\.fr\.debian\.org/g' /etc/apt/sources.list.d/debian.sources
RUN apt-get update
RUN apt-get install -y --no-install-recommends libfreetype6-dev libjpeg62-turbo-dev libpng-dev libicu-dev libzip-dev libxml2-dev wkhtmltopdf libwebp-dev
# Installation des extensions PHP
RUN docker-php-ext-configure gd --enable-gd --with-freetype --with-jpeg --with-webp
RUN docker-php-ext-install -j$(nproc) gd
RUN docker-php-ext-install opcache zip pdo_mysql intl soap
RUN pecl install apcu-5.1.21
RUN docker-php-ext-enable apcu
# Installation de composer
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php composer-setup.php
RUN mv composer.phar /usr/local/bin/composer

