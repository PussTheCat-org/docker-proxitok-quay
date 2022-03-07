FROM php:apache
WORKDIR /var/www/html
RUN apt update -y && apt upgrade -y \
    && apt install -y --no-install-recommends wget \
    && apt autoclean -y \
    && apt autoremove -y \
    && rm -rf /var/lib/apt/lists/* \
    && wget https://raw.githubusercontent.com/composer/getcomposer.org/main/web/installer -O - -q | php -- --quiet \
    && git clone --depth=1 https://github.com/pablouser1/ProxiTok.git . \
    && composer install
EXPOSE 80
CMD ["httpd-foreground"]
