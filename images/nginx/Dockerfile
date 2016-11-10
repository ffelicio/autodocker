FROM nginx

MAINTAINER Danilo Correa <danilosilva87@gmail.com>

ADD nginx.conf /etc/nginx/
COPY hosts/*.conf /etc/nginx/sites-available/

CMD ["nginx"]

EXPOSE 80 443
