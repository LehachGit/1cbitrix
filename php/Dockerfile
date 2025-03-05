# Используем стабильную версию PHP 8.2 с FPM
FROM php:8.2-fpm

# Устанавливаем необходимые PHP-расширения для Bitrix
RUN apt-get update && apt-get install -y \
    libpng-dev \
    libjpeg-dev \
    libfreetype6-dev \
    libzip-dev \
    unzip \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install gd zip mysqli pdo pdo_mysql opcache

# Копируем кастомный php.ini (по желанию)
COPY php.ini /usr/local/etc/php/php.ini

# Создаем рабочую директорию
WORKDIR /var/www/html