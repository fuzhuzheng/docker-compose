# docker-compose
Awesome Docker Compose samples
docker run -itd --name php 
--net mynetwork 
--ip 172.18.0.4 
--restart=always 
-v "$PWD":/wwwroot 
-w /wwwroot 
php:7.4.6-fpm