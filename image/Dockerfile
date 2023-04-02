FROM alpine:3.2

#setup
RUN  apk update && apk upgrade && \
     apk add bash \
     imagemagick \
     curl


# Apache
RUN  apk add apache2


# php
RUN  apk add php \
     php-apache2 \
     php-phar \
     php-json \
     php-iconv \
     php-openssl \
     php-ftp \
     # php-xdebug \
     php-mcrypt \
     php-soap \
     php-gmp \
     php-pdo_odbc \
     php-dom \
     php-pdo \
     php-zip \
     php-mysqli \
     php-sqlite3 \
     php-pdo_pgsql \
     php-bcmath \
     php-gd \
     php-odbc \
     php-pdo_mysql \
     php-pdo_sqlite \
     php-gettext \
     php-xmlreader \
     php-xmlrpc \
     php-bz2 \
     php-pdo_dblib \
     php-curl \
     php-ctype \
     php-exif \
     php-zlib

#Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer && \
     composer self-update 1.10.26


RUN echo "ServerName localhost" >> /etc/apache2/httpd.conf
RUN echo "LoadModule filter_module modules/mod_filter.so" >> /etc/apache2/httpd.conf
# RUN echo "LoadModule deflate_module modules/mod_deflate.so" >> /etc/apache2/httpd.conf


EXPOSE 80

CMD  [ "/usr/sbin/httpd", "-D", "FOREGROUND", "-f", "/etc/apache2/httpd.conf"]



