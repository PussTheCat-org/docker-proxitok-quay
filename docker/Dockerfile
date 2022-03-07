FROM php:apache
WORKDIR /var/www/html
RUN apt update -y && apt upgrade -y \
    && apt install -y --no-install-recommends wget git \
    && apt autoclean -y \
    && apt autoremove -y \
    && rm -rf /var/lib/apt/lists/* \
    && rm -rf /var/www/html/*

COPY --from=composer /usr/bin/composer /usr/bin/composer

RUN git clone --depth=1 https://github.com/pablouser1/ProxiTok.git . \
    && composer install

EXPOSE 80
CMD ["httpd-foreground"]
