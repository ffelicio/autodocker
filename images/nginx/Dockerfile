FROM nginx:1.11.5-alpine

MAINTAINER Danilo Correa <danilosilva87@gmail.com>

ARG USER_PUID=1000
ARG USER_PGID=1000
ARG USER_NAME=${USER_NAME}

RUN addgroup -g $USER_PGID -S $USER_NAME
RUN adduser -u $USER_PUID $USER_NAME -G $USER_NAME -D

ADD nginx.conf /etc/nginx/
COPY hosts/*.conf /etc/nginx/sites-available/

CMD ["nginx"]

EXPOSE 80 443
