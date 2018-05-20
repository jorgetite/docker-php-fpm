# *************************************************************************** #
#  PHP 7.1-FPM image based on Alpine Linux                                    #
# *************************************************************************** #
FROM alpine:latest

LABEL maintainer="jorgetite@me.com"

# Use CODECAST custom repo
ADD https://php.codecasts.rocks/php-alpine.rsa.pub /etc/apk/keys/php-alpine.rsa.pub
RUN apk --update add ca-certificates wget curl
RUN echo "@php https://php.codecasts.rocks/v3.7/php-7.1" >> /etc/apk/repositories

RUN apk add --update \
    php@php \
    php-bcmath@php \
    php-bz2@php \
    php-calendar@php \
    php-ctype@php \
    php-curl@php \
    php-dom@php \
    php-embed@php \
    php7-exif@php \
    php7-ftp@php \
    php-gd@php \
    php-gettext@php \
    php-gmp@php \
    php-iconv@php \
    php-imagick@php \
    php-imap@php \
    php-intl@php \
    php-json@php \
    php7-ldap@php \
    php-mbstring@php \
    php7-mongodb@php \
    php-mysqlnd@php \
    php7-odbc@php \
    php-opcache@php \
    php-openssl@php \
    php7-pcntl@php \
    php-pdo@php \
    php7-pdo_dblib@php \
    php-pdo_mysql@php \
    php-pdo_odbc@php \
    php-pdo_pgsql@php \
    php-pdo_sqlite@php \
    php-pgsql@php \
    php-phar@php \
    php-posix@php \
    php7-redis@php \
    php-session@php \
    php-soap@php \
    php-sockets@php \
    php-sqlite3@php \
    php7-sysvmsg@php \
    php7-sysvsem@php \
    php7-sysvshm@php \
    php-xml@php \
    php-xmlreader@php \
    php7-xmlrpc@php \
    php7-xsl@php \
    php-zip@php \
    php-zlib@php \
    php7-fpm@php

# ensure www-data user exists
RUN set -x \
	&& addgroup -g 82 -S www-data \
	&& adduser -u 82 -D -S -G www-data www-data
# 82 is the standard uid/gid for "www-data" in Alpine
# http://git.alpinelinux.org/cgit/aports/tree/main/apache2/apache2.pre-install?h=v3.3.2
# http://git.alpinelinux.org/cgit/aports/tree/main/lighttpd/lighttpd.pre-install?h=v3.3.2
# http://git.alpinelinux.org/cgit/aports/tree/main/nginx-initscripts/nginx-initscripts.pre-install?h=v3.3.2

# PHP-FPM config
COPY php-fpm-override.conf /etc/php7/php-fpm.d/zz-php-fpm.conf
COPY php-fpm-fg /usr/local/bin/

# Fix permissions
RUN chmod +x /usr/local/bin/php-fpm-fg

EXPOSE 9000
CMD ["php-fpm-fg"]