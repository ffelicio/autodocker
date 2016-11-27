FROM php:5.6.28-fpm-alpine

MAINTAINER Danilo Correa <danilosilva87@gmail.com>

# Instalando curl, libmemcached-dev, libz-dev, libjpeg-dev, libpng12-dev, libfreetype6-dev, libssl-dev, libmcrypt-dev
RUN apk add --no-cache --virtual \    
        git \
        libmemcached-dev \
        libz-dev \
        libpq-dev \
        libjpeg-dev \
        libpng12-dev \
        libfreetype6-dev \
        libssl-dev \
        libmcrypt-dev \
        libxrender1 \
        libfontconfig1 \
        libxext6

# Instalando extensão php mycrypt
RUN docker-php-ext-install mcrypt

# Instalando extensão php pdo_mysql
RUN docker-php-ext-install pdo_mysql

# Instalando extensão php pdo_pgsql
RUN docker-php-ext-install pdo_pgsql

# Instalando PHP biblioteca gd
RUN docker-php-ext-install gd

# Instalação opcional da extensão do xdebug
ARG INSTALL_XDEBUG=true
RUN if [ ${INSTALL_XDEBUG} = true ]; then \
    pecl install xdebug && \
    docker-php-ext-enable xdebug \
;fi


# Instalação opcional da extensão do mongodb
ARG INSTALL_MONGO=true
RUN if [ ${INSTALL_MONGO} = true ]; then \
    pecl install mongodb && \
    docker-php-ext-enable mongodb \
;fi

# Instalação opcional da extensão do zip
ARG INSTALL_ZIP_ARCHIVE=true
RUN if [ ${INSTALL_ZIP_ARCHIVE} = true ]; then \
    pecl install zip && \
    docker-php-ext-enable zip \
;fi

# Instalação opcional da extensão do opcache
ARG INSTALL_OPCACHE=true
RUN if [ ${INSTALL_OPCACHE} = true ]; then \
    docker-php-ext-install opcache && \
    docker-php-ext-enable opcache \
;fi

ARG USER_PUID=1000
ARG USER_PGID=1000
ARG USER_NAME=${USER_NAME}

RUN addgroup -g $USER_PGID -S $USER_NAME
RUN adduser -u $USER_PUID $USER_NAME -G $USER_NAME -D


# Instalação do composer
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && \
    php -r "if (hash_file('SHA384', 'composer-setup.php') === 'aa96f26c2b67226a324c27919f1eb05f21c248b987e6195cad9690d5c1ff713d53020a02ac8c217dbf90a7eacc9d141d') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;" && \
    php composer-setup.php && \
    php -r "unlink('composer-setup.php');"

RUN mv composer.phar /usr/local/bin/composer
RUN chown -R autodocker:autodocker /usr/local/bin/composer

# Adicionado arquivo do php.ini
ADD ./php.ini /usr/local/etc/php/conf.d
ADD ./www.conf /usr/local/etc/php-fpm.d/

CMD ["php-fpm"]