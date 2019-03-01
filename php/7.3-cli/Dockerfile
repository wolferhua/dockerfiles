FROM  php:7.3-cli

MAINTAINER wolferhua

COPY ./sources.list /etc/apt/sources.list

# 环境安装
RUN apt update \
    && apt upgrade -y \
    && ln -s /usr/lib/x86_64-linux-gnu/libssl.so  /usr/lib \
    && apt install  -y \
        libfreetype6-dev \
        libmcrypt-dev \ 
        libjpeg-dev \
        libpng-dev \
        sendmail \
        openssl \ 
        libssl-dev \
        libzip-dev \
        wget \
        zlib1g-dev -y \
    && docker-php-ext-configure gd \
            --enable-gd-native-ttf \
            --with-freetype-dir=/usr/include/freetype2 \
            --with-png-dir=/usr/include \
            --with-jpeg-dir=/usr/include \
    && docker-php-ext-install gd pdo pdo_mysql opcache pcntl mysqli \
    && pecl install redis \
    && pecl install mongodb \
    && pecl install swoole\
    && docker-php-ext-enable redis mongodb swoole pcntl \
    && wget https://dl.laravel-china.org/composer.phar -O /usr/local/bin/composer \
    && chmod +x /usr/local/bin/composer
#docker build -t wolferhua/php:7.3-cli .








