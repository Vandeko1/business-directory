FROM php:8.2-apache

# Встановлення необхідних розширень PHP
RUN apt-get update && apt-get install -y \
    git unzip libpq-dev libonig-dev libzip-dev \
    && docker-php-ext-install pdo pdo_mysql mbstring zip

# Встановлення Composer
COPY --from=composer:2.6 /usr/bin/composer /usr/bin/composer

# Налаштування робочої директорії
WORKDIR /var/www/html

# Копіювання проєкту
COPY . /var/www/html

# Встановлення прав
RUN chown -R www-data:www-data /var/www/html

# Увімкнення модулів Apache
RUN a2enmod rewrite

EXPOSE 80
