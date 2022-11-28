# docker-compose
Awesome Docker Compose samples

docker run -itd --name myredis --net mynetwork --ip 172.18.0.2 --restart=always -v /home/docker/redis/conf/redis.conf:/etc/redis/redis.conf -v /home/docker/redis/data:/data redis:5.0.7 redis-server /etc/redis/redis.conf