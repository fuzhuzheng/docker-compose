FROM hyperf/hyperf:8.0-alpine-v3.15-swoole-v4.8.10

LABEL maintainer="Hyperf Developers <group@hyperf.io>" version="1.0" license="MIT"

ARG timezone

ENV PHPIZE_DEPS="autoconf dpkg-dev dpkg file gcc g++ libc-dev make php8-dev php8-pear pkgconf re2c pcre-dev pcre2-dev zlib-dev libtool automake" \
    TIMEZONE=${timezone:-"Asia/Shanghai"}

RUN set -ex \
    && apk add --no-cache protobuf \
    && apk add --no-cache --virtual .build-deps $PHPIZE_DEPS \
    && cd /tmp \
    && pecl8 install protobuf \
    && echo "extension=protobuf.so" > /etc/php8/conf.d/protobuf.ini \
    # show php version and extensions
    && php -v \
    && php -m \
    && php --ri swoole \
    #  ---------- some config ----------
    && cd /etc/php8 \
    # - config PHP
    && { \
        echo "upload_max_filesize=128M"; \
        echo "post_max_size=128M"; \
        echo "memory_limit=1G"; \
        echo "date.timezone=${TIMEZONE}"; \
    } | tee conf.d/99_overrides.ini \
    # - config timezone
    && ln -sf /usr/share/zoneinfo/${TIMEZONE} /etc/localtime \
    && echo "${TIMEZONE}" > /etc/timezone \
    # ---------- clear works ----------
    && apk del .build-deps \
    && rm -rf /var/cache/apk/* /tmp/* /usr/share/man /usr/local/bin/php*

