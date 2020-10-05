# Commands

```
docker run -d -e MYSQL_ALLOW_EMPTY_PASSWORD=true mysql
docker run -d -e MYSQL_ALLOW_EMPTY_PASSWORD=true -v $(pwd)/mysql-data:/var/lib/mysql mysql
docker run -d -e MYSQL_ALLOW_EMPTY_PASSWORD=true -v mysql-data:/var/lib/mysql mysql
```

```
docker exec -it CONTAINER_ID mysql
create database DB_NAME; show databases; exit
```

```
docker stop CONTAINER_ID
docker rm CONTAINER_ID
```
