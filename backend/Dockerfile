# Використовуємо базовий образ з PHP 8.2 та Apache
FROM php:8.2-apache

# Оновлення пакунків та встановлення необхідних бібліотек
RUN apt-get update && apt-get install -y \
    git \
    unzip \
    libpq-dev \
    libonig-dev \
    libzip-dev \
    && apt-get clean

# Встановлення PHP розширень для роботи з MySQL, пдф, і т.д.
RUN docker-php-ext-install pdo pdo_mysql mbstring zip

# Встановлення Composer (для менеджменту залежностей)
COPY --from=composer:2.6 /usr/bin/composer /usr/bin/composer

# Налаштування робочої директорії
WORKDIR /var/www/html

# Копіювання проекту в контейнер
COPY . /var/www/html

# Встановлення прав на файли
RUN chown -R www-data:www-data /var/www/html

# Увімкнення Apache модулів, таких як rewrite
RUN a2enmod rewrite

# Встановлення налаштувань для Apache
RUN echo "ServerName localhost" >> /etc/apache2/apache2.conf

# Встановлення змінної середовища для коректного розташування веб-директорії
ENV APACHE_DOCUMENT_ROOT /var/www/html/web

# Оновлення конфігурації Apache для роботи з коректним коренем документа
COPY ./apache-config/000-default.conf /etc/apache2/sites-available/000-default.conf

# Відкриття порту 80 для Apache
EXPOSE 80

# Запуск Apache в передньому плані
CMD ["apache2-foreground"]
