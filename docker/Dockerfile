FROM php:8.1-fpm

RUN apt-get update && apt-get install -y \
    git \
    unzip \
    curl \
    libzip-dev \
    zip \
    && docker-php-ext-install zip pdo pdo_mysql

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /var/www/html

COPY ../app /var/www/html

RUN composer install

RUN chown -R www-data:www-data /var/www/html

EXPOSE 9000
CMD ["php-fpm"]
