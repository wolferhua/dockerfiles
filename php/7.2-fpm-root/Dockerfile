FROM wolferhua/php:7.2-fpm

MAINTAINER wolferhua

COPY  docker-php-entrypoint /usr/local/bin/

ENTRYPOINT ["docker-php-entrypoint"]

CMD ["php-fpm"]

#docker build -t wolferhua/php:7.2-fpm-root .