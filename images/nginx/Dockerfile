FROM nginx

MAINTAINER Danilo Correa <danilosilva87@gmail.com>

ARG PUID=1000
ARG PGID=1000
RUN groupadd -g 1000 autodocker && \
    useradd -u 1000 -g autodocker -m autodocker

ADD nginx.conf /etc/nginx/
COPY hosts/*.conf /etc/nginx/sites-available/


CMD ["nginx"]

EXPOSE 80 443
