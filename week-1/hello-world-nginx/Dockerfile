FROM ubuntu

RUN apt-get update && apt-get install -y nginx

RUN ln -sf /dev/stdout /var/log/nginx/access.log
RUN ln -sf /dev/stderr /var/log/nginx/error.log

COPY index.html /var/www/html/index.nginx-debian.html

CMD ["nginx", "-g", "daemon off;"]
