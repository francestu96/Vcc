FROM php:7.2-apache

WORKDIR /var/www/html
ADD https://files.phpmyadmin.net/phpMyAdmin/4.9.1/phpMyAdmin-4.9.1-all-languages.tar.gz /var/www/html
RUN tar xvfz phpMyAdmin-4.9.1-all-languages.tar.gz --strip 1
RUN tar -C /usr/local/bin -xvzf dockerize-linux-amd64-v0.6.1.tar.gz
RUN rm -f *.tar.gz
RUN docker-php-ext-install mysqli

ADD config.inc.php config.inc.php
ADD set-env.sh /usr/local/bin/

RUN chmod a+x /usr/local/bin/set-env.sh; 
RUN sed -i "3iset-env.sh" /usr/local/bin/docker-php-entrypoint
