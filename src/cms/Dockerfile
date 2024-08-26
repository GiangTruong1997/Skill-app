FROM wyveo/nginx-php-fpm:php82


RUN pip install supervisor \
    && pip install git+https://github.com/coderanger/supervisor-stdout


WORKDIR /var/www/html
RUN chown -R www-data:www-data /var/www/html

COPY ./composer.json /var/www/html/
COPY ./composer.lock /var/www/html/
RUN  composer install --optimize-autoloader --no-dev
COPY . /var/www/html

RUN chmod -R 777 /var/www/html/bootstrap
RUN chmod -R 777 /var/www/html/storage
