FROM php:apache
ENV GH_TOKEN=$(cat /run/secrets/gh_token) # https://docs.docker.com/engine/reference/builder/#arg
WORKDIR /var/www/html
COPY --from=composer /usr/bin/composer /usr/bin/composer
RUN --mount=type=secret,id=gh_token apt update -y && apt upgrade -y \
    && apt install -y --no-install-recommends wget git \
    && apt autoclean -y \
    && apt autoremove -y \
    && rm -rf /var/lib/apt/lists/* \
    && rm -rf /var/www/html/* \
    && pecl install redis \
    && docker-php-ext-enable redis \
    && git clone --depth=1 https://github.com/pablouser1/ProxiTok.git . \
    && composer config -g github-oauth.github.com $GH_TOKEN \
    && composer update \
    && composer install

EXPOSE 80
CMD ["httpd-foreground"]
