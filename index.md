# docker镜像迁移

#### 1、打包
```
docker save -o mynetcore.tar mynetcore:v1
```

#### 2、传输
```
rsync -av --progress mynetcore.tar root@49.233.9.236:~/
```

#### 3、加载
```
docker load -i mynetcore.tar
```

```
mysql
docker run --name mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=123456 -d mysql:8.0

redis
docker run --name myredis -p 6379:6379 -d redis redis-server

发布后的netcore
docker run --name=datavisual2 -d -p 8056:80 -v ~/datavisual2/PublishDocker:/app mynetcore:1.1

vue
docker run --name vuedatavisual -p 8000:8000 -d nginx:v1

图片服务器
docker run -d --name image -p 8089:80 -v ~/datavisual2/PublishDocker/wwwroot/UploadFile:/home/images image:v1
```
