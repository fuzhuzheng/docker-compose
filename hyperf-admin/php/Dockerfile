FROM hyperf/hyperf:7.3-alpine-v3.11-swoole-v4

WORKDIR /data/project

RUN composer install --no-dev -o

EXPOSE 9501

CMD ["php", "/data/project/bin/hyperf.php", "start"]