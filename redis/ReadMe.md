[toc]
## 添加 docker-compose.yml
```
version : '2'
services:
   redis:
      image: redis
      ports:
          - "6379:6379"
      container_name: redis
      networks:
          - "netName1"
      volumes:
          #- /opt/conf/:/mnt/
          - /usr/local/www/redis:/etc/redis
          #- /usr/local/www/redis/redis.conf:/usr/local/etc/redis/redis.conf
      command: redis-server /etc/redis/redis.conf 
        # requirepass dzq123456

networks:
      netName1:
         driver: bridge

```
## 遇到坑
daemonize no 默认情况下，redis不是在后台运行的，如果需要在后台运行，把该项的值更改为yes


**必须改成 no 才可以启动**
```
daemonize no
```

## 配置 redis.conf 
需要把 bind 127.0.0.1 屏蔽
```
#bind 127.0.0.1
```
## 运行命令
1. 创建并运行容器
```
docker-compose up -d
docker-compose up 
```
2. 停止
```
docker-compose stop redis

```
3. 删除容器
```
docker-compose rm redis

```
