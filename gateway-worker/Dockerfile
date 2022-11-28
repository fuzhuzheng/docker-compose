FROM php:7.4-cli-alpine
RUN apk --update add \
    libevent-dev &&  \
    pecl install event-3.0.8 && \
    docker-php-ext-enable event &&  \
    docker-php-ext-install opcache pcntl opcache && \
    docker-php-ext-enable opcache && \
    rm -rf /var/cache/apk/*