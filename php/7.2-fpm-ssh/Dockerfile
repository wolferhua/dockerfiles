FROM wolferhua/php:7.2-fpm

MAINTAINER wolferhua

# 环境安装
RUN apt update \
    && apt upgrade -y \
    && apt install ssh git -y
COPY  docker-php-entrypoint /usr/local/bin/

#docker build -t wolferhua/php:7.2-fpm-ssh .







