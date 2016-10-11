FROM php:5.6-fpm

MAINTAINER Danilo Correa <danilosilva87@gmail.com>

# Instalando curl, libmemcached-dev, libz-dev, libjpeg-dev, libpng12-dev, libfreetype6-dev, libssl-dev, libmcrypt-dev
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        curl \
        libmemcached-dev \
        libz-dev \
        libpq-dev \
        libjpeg-dev \
        libpng12-dev \
        libfreetype6-dev \
        libssl-dev \
        libmcrypt-dev

# Instalando extensão php mycrypt
RUN docker-php-ext-install mcrypt

# Instalando extensão php pdo_mysql
RUN docker-php-ext-install pdo_mysql

# Instalando extensão php pdo_pgsql
RUN docker-php-ext-install pdo_pgsql

# Instalando PHP biblioteca gd
RUN docker-php-ext-install gd && \
    docker-php-ext-configure gd \
        --enable-gd-native-ttf \
        --with-jpeg-dir=/usr/lib \
        --with-freetype-dir=/usr/include/freetype2 && \
    docker-php-ext-install gd

# Instalação opcional da extensão do xdebug
ARG INSTALL_XDEBUG=true
RUN if [ ${INSTALL_XDEBUG} = true ]; then \
    pecl install xdebug && \
    docker-php-ext-enable xdebug \
;fi

# Copiando extensão do xdebug para o cointainer
COPY ./xdebug.ini /usr/local/etc/php/conf.d/xdebug.ini
#ADD ./../xdebug.ini /usr/local/etc/php/conf.d

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

# Instalação opcional da extensão do memcached
ARG INSTALL_MEMCACHED=true
RUN if [ ${INSTALL_MEMCACHED} = true ]; then \
    pecl install memcached && \
    docker-php-ext-enable memcached \
;fi

# Instalação opcional da extensão do opcache
ARG INSTALL_OPCACHE=true
RUN if [ ${INSTALL_OPCACHE} = true ]; then \
    docker-php-ext-install opcache && \
    docker-php-ext-enable opcache \
;fi

# Copiando arquivo de configuração para o container
COPY ./opcache.ini /usr/local/etc/php/conf.d/opcache.ini

# Adicionado arquivo do php.ini
#ADD ./php.ini /usr/local/etc/php/conf.d
#ADD ./www.conf /usr/local/etc/php-fpm.d/

RUN rm -r /var/lib/apt/lists/*

CMD ["php-fpm"]