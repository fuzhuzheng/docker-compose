FROM php:7.4.33-zts-alpine
RUN apk --update add \
    libevent-dev autoconf &&  \
    pecl install event && \
    docker-php-ext-enable event &&  \
    docker-php-ext-install opcache pcntl opcache && \
    docker-php-ext-enable opcache && \
    rm -rf /var/cache/apk/*