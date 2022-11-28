FROM php:7.4-cli-alpine

RUN set -ex && \
    apk --update add libevent-dev &&  \
    pecl install event && \
    docker-php-ext-enable event &&  \
    docker-php-ext-install opcache pcntl opcache && \
    docker-php-ext-enable opcache && \
    rm -rf /var/cache/apk/* /tmp/* /usr/share/man && \
    echo -e "\033[42;37m Build Completed :).\033[0m\n"
