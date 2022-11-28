FROM php:7.4.33-zts-alpine

ENV PHPIZE_DEPS="autoconf g++ gcc automake openssl"

RUN set -ex && \
    apk add --no-cache --virtual .build-deps $PHPIZE_DEPS && \
    apk --update add libevent-dev &&  \
    pecl install event && \
    docker-php-ext-enable event &&  \
    docker-php-ext-install opcache pcntl opcache && \
    docker-php-ext-enable opcache && \
    apk del .build-deps && \
    rm -rf /var/cache/apk/* /tmp/* /usr/share/man && \
    echo -e "\033[42;37m Build Completed :).\033[0m\n"
