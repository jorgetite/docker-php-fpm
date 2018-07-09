# Docker PHP-FPM

Docker images providing support for [PHP-FPM](https://php-fpm.org) on Alpine Linux. PHP-FPM (FastCGI Process Manager) is an alternative PHP FastCGI implementation with some additional features useful for sites of any size, especially busier sites. 

## Images

| Alpine Version  | PHP Version   | Repository         | Tag     | Dockerfile
|---              |---            |---                 |---      |---
|  3.7            | 7.2           | jorgetite/php-fpm  | latest  |  [docker-php-fpm/php-72/Dockerfile](https://github.com/jorgetite/docker-php-fpm/blob/master/php-72/Dockerfile)
|  3.7            | 7.1           | jorgetite/php-fpm  | 71      |  [docker-php-fpm/php-72/Dockerfile] (https://github.com/jorgetite/docker-php-fpm/blob/master/php-71/Dockerfile)

## Usage

### Creating a new container
```Shell
docker run -d --name app-php-fpm -p 9000:9000 -v /local/path/to/webapp:/var/www:rw jorgetite/php-fpm
```

## Extensions

The following extensions are included on each image:

* bz2
* calendar
* ctype
* curl
* dom
* embed
* exif
* ftp
* gd
* gettext
* gmp
* iconv
* imagick
* imap
* intl
* json
* ldap
* mbstring
* mongodb
* mysqlnd
* odbc
* opcache
* openssl
* pcntl
* pdo
* pdo_dblib
* pdo_mysql
* pdo_odbc
* pdo_pgsql
* pdo_sqlite
* pgsql
* phar
* posix
* redis
* session
* soap
* sockets
* sqlite3
* sysvmsg
* sysvsem
* sysvshm
* xml
* xmlreader
* xmlrpc
* xsl
* zip
* zlib

## PHP Repositories
PHP and extensions are based on repositories maintained by [Codecast](https://github.com/codecasts/php-alpine).

## License
The files contained in this project are released under the MIT License. You can find a copy of this license in LICENSE.txt file.