
FROM php:8.1-apache

RUN apt-get update && apt-get install -y \
    libcurl4-openssl-dev pkg-config libssl-dev \
    && docker-php-ext-install mysqli pdo pdo_mysql

RUN pecl install phalcon && docker-php-ext-enable phalcon

RUN a2enmod rewrite

COPY ./public /var/www/html

WORKDIR /var/www/html

EXPOSE 80

CMD ["apache2-foreground"]
