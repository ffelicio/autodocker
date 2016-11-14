FROM nginx

MAINTAINER Danilo Correa <danilosilva87@gmail.com>

ARG USER_PUID=1000
ARG USER_PGID=1000
ARG USER_NAME=${USER_NAME}
RUN groupadd -g $USER_PGID $USER_NAME && \
    useradd -u $USER_PUID -g $USER_NAME -m $USER_NAME    

ADD nginx.conf /etc/nginx/
COPY hosts/*.conf /etc/nginx/sites-available/

CMD ["nginx"]

EXPOSE 80 443
