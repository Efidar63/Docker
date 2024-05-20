FROM php:7.3-apache
USER root
RUN apt-get update \
    && apt-get install -y mariadb-client-10.5 \
    && rm -rf /var/lib/apt/lists/
RUN docker-php-ext-install mysqli && docker-php-ext-enable mysqli
RUN mkdir /var/www/html/images
RUN chmod 777 /var/www/html/images
COPY ./php/ /var/www/html/
WORKDIR /var/www/html
EXPOSE 80
CMD ["apache2-foreground"]