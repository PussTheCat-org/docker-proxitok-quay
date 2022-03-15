FROM php:8-apache
WORKDIR /var/www/html
COPY --from=composer /usr/bin/composer /usr/bin/composer
ARG GH_TOKEN
RUN apt update -y && apt upgrade -y \
    && apt install -y --no-install-recommends git libzip-dev \
    && pecl install redis zip \
    && docker-php-ext-enable redis zip \
    && a2enmod rewrite headers \
    && mkdir /cache \
    && chown -R www-data:www-data /cache \
    && git clone --depth=1 https://github.com/pablouser1/ProxiTok.git . \
    && composer config -g github-oauth.github.com "$GH_TOKEN" \
    && composer update \
    && composer install --no-interaction --optimize-autoloader --no-dev \
    && apt autoclean -y \
    && apt autoremove -y \
    && rm -rf /var/lib/apt/lists/* \
    && rm -rf /var/www/html/* \
    && rm -rf /usr/bin/composer

EXPOSE 80
