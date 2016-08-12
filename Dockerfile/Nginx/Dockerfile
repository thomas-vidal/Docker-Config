FROM debian:8
MAINTAINER Thomas Vidal <thomsvdl@gmail.com>

RUN apt-get upgrade && apt-get update
RUN apt-get -y install wget curl python

RUN wget http://nginx.org/keys/nginx_signing.key && apt-key add nginx_signing.key
RUN apt-get update && apt-get -y install nginx

RUN ln -sf /var/www/html /www && ln -sf /etc/nginx/site-available /site

VOLUME ["/www", "/site"]

EXPOSE 80 443

CMD ["nginx", "-g", "daemon off;"]
