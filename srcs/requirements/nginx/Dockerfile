FROM debian:bullseye

RUN apt-get update && apt-get install -y nginx openssl

EXPOSE 443

COPY ./conf/default/ /etc/nginx/sites-enabled/default
COPY ./tools/nginx_start.sh /var/www

RUN chmod +x /var/www/nginx_start.sh

ENTRYPOINT ["var/www/nginx_start.sh"] 

CMD ["nginx", "-g", "daemon off;"]

