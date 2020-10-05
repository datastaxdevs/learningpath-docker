# Commands to start wordpress manually

```
docker network create wp --driver bridge
docker run --detach -v mysql_data:/var/lib/mysql --network wp --name database -e MYSQL_ROOT_PASSWORD=secretpassword -e MYSQL_DATABASE=wordpress -e MYSQL_USER=wordpress -e MYSQL_PASSWORD=wordpress mysql:5
docker run -p 80:80 -v wp_data:/var/www/html --network wp --detach -e WORDPRESS_DB_HOST=database:3306 -e WORDPRESS_DB_USER=wordpress -e WORDPRESS_DB_PASSWORD=wordpress -e WORDPRESS_DB_NAME=wordpress wordpress:latest
```

# Commands to start wordpress with docker-compose

```
docker-compose up -d
```

See [docker-compose.yaml](./docker-compose.yaml) for more details.