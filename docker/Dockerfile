FROM php:7.4-apache
WORKDIR /var/www/html
COPY --from=composer /usr/bin/composer /usr/bin/composer
ARG GH_TOKEN
RUN apt update -y && apt upgrade -y \
    && apt install -y --no-install-recommends wget git zip unzip php7.4-zip \
    && apt autoclean -y \
    && apt autoremove -y \
    && rm -rf /var/lib/apt/lists/* \
    && rm -rf /var/www/html/* \
    && pecl install redis \
    && docker-php-ext-enable redis zip \
    && a2enmod rewrite headers \
    && git clone --depth=1 https://github.com/pablouser1/ProxiTok.git . \
    && composer config -g github-oauth.github.com "$GH_TOKEN" \
    && composer update \
    && composer install

EXPOSE 80
