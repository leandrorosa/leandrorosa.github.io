---
title: "Guava Cache with Java 8 Lambdas"
date: 2019-03-14T05:27:05-03:00
draft: false
tags: 
---
Today I  needed to cache some values in memory in an application that does a lot of json parsing and I tought that Guava Cache would be nice for that.

### Creating the cache
To create the cache we use a CacheBuilder and setup the properties in it.

```java
private static final Cache<Integer, String> cache =
      CacheBuilder.newBuilder()
          .weakValues()
          .maximumSize(CACHE_SIZE)
          .build(
              new CacheLoader<Integer, String>() {
                @Override
                public String load(Integer key) throws Exception {
                  return "my computed value";
                }
              });
``` 
Sounds a little bit verbose, maybe we can use Jaba 8 lambdas instead of the CacheLoader?

### Using Java 8 lambdas
There's a way you can separate the creation of the cache from it's use, so you can isolate the cache configuration from the business logic.

Creation:
```java
private static final Cache<Integer, String> cache =
      CacheBuilder.newBuilder()
          .weakValues()
          .maximumSize(CACHE_SIZE)          
          .build();
```

Using the cache:
```java
cache.get(key, () ->  "my computed value");
```
Much more cleaner :)

### Reference
- [Guava Cache docs](https://github.com/google/guava/wiki/CachesExplained)
- [Guava Cache from a callable](https://github.com/google/guava/wiki/CachesExplained)
