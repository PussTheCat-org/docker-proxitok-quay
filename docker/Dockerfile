FROM php:8
WORKDIR /proxitok
COPY --from=composer /usr/bin/composer /usr/bin/composer
ARG GH_TOKEN
RUN apt update -y && apt upgrade -y \
    && apt install -y --no-install-recommends wget git unzip libzip-dev \
    && pecl install redis \
    && docker-php-ext-enable redis \
    && docker-php-ext-install zip \
    && docker-php-ext-enable zip \
    && a2enmod rewrite headers \
    && git clone --depth=1 https://github.com/pablouser1/ProxiTok.git . \
    && composer config -g github-oauth.github.com "$GH_TOKEN" \
    && composer update \
    && composer install \
    && apt autoclean -y \
    && apt autoremove -y \
    && rm -rf /var/lib/apt/lists/* \
    && rm -rf /var/www/html/* \
    && rm -rf /usr/bin/composer

EXPOSE 8080
CMD php -S 0.0.0.0:8080