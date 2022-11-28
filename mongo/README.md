# docker-compose
Awesome Docker Compose samples


docker run -itd --net mynetwork --ip 172.18.0.7 --restart=always --name mymongodb --v /home/docker/mongodb/data:/data/db mongo:4.2.8 --auth