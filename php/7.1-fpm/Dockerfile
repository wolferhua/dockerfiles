FROM daocloud.io/php:7.1-fpm

MAINTAINER wolferhua

# 环境安装
RUN sed -i 's/deb.debian.org/mirrors.ustc.edu.cn/g' /etc/apt/sources.list \
    && apt update \
    && apt upgrade -y \
    && pecl install redis \
    && ln -s /usr/lib/x86_64-linux-gnu/libssl.so  /usr/lib \
    && apt install  -y \
        libfreetype6-dev \
        libmcrypt-dev \
        libpng12-dev \
        libjpeg-dev \
        libpng-dev \
        sendmail \
        openssl \
        libpng-dev \
        libssl-dev \
        wget \
    && apt install zlib1g-dev -y \
    && pecl install mongodb \
    && docker-php-ext-configure gd \
            --enable-gd-native-ttf \
            --with-freetype-dir=/usr/include/freetype2 \
            --with-png-dir=/usr/include \
            --with-jpeg-dir=/usr/include \
    && docker-php-ext-install mbstring zip gd pdo pdo_mysql opcache pcntl\
    && pecl install swoole-2.1.1 \
    && docker-php-ext-enable redis mongodb swoole  pcntl\
    && wget https://dl.laravel-china.org/composer.phar -O /usr/local/bin/composer \
    && chmod +x /usr/local/bin/composer

#docker build -t wolferhua/php:7.1-fpm .








