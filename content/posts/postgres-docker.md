---
title: "Running PostgreSQL through Docker"
date: 2019-01-02T15:11:05-02:00
draft: false
tags: docker
---
I've been using Docker to run PostgreSQL server and I think it is much simplier than installing it natively. 

### Creating container
```
docker run --name postgres -e POSTGRES_PASSWORD=postgres -p 5432:5432 -v /home/user/postgres/data:/var/lib/postgresql/data -d postgres
``` 

Note: You can customize `/home/users/postgres/data` directory 

### Starting server
```
sudo docker start postgres
```

### Stopping server
```
sudo docker stop postgres
```
