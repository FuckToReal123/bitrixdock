FROM nginx:latest

COPY conf/nginx.conf /etc/nginx/
COPY conf/default.conf /etc/nginx/templates/conf.d/
COPY conf/upstream.conf /etc/nginx/conf.d/

WORKDIR /var/www/

RUN apt-get install gettext-base

RUN usermod -u 1000 www-data

CMD sh -c "envsubst \"`env | awk -F = '{printf \" \\\\$%s\", $1}'`\" < /etc/nginx/templates/conf.d/default.conf > /etc/nginx/conf.d/default.conf && nginx -g 'daemon off;'"
