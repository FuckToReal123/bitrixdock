FROM httpd:2.4.25

RUN usermod -u 1000 www-data

COPY conf/httpd.conf /usr/local/apache2/conf/httpd.conf
COPY conf/default.conf /usr/local/apache2/conf.d/default.conf

WORKDIR /var/www/
