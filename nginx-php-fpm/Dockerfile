FROM richarvey/nginx-php-fpm:1.7.4

RUN set -ex && \
    docker-php-ext-install opcache pcntl opcache bcmath sockets xmlrpc sysvsem shmop && \
    docker-php-ext-enable opcache && \
    apk --update add libevent-dev autoconf &&  \
    pecl install event && \
    docker-php-ext-enable event &&  \
    rm -rf /var/cache/apk/* /tmp/* /usr/share/man && \
    echo -e "\033[42;37m Build Completed :).\033[0m\n"

#[PHP Modules]
#bcmath
#event
#gettext
#pcntl
#shmop
#sockets
#sysvsem
#xmlrpc
