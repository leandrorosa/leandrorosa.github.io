---
title: "Formatting code with Spotless maven plugin"
date: 2019-01-28T05:31:05-02:00
draft: true
tags: 
---
I'd  started a new Spring Boot recently and had found a better way to check up the code format. I usually do this with IDE setup
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
