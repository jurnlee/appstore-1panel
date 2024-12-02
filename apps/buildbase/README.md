# BuildBase

[![Docker Automated build](https://img.shields.io/docker/automated/jlesage/baseimage-gui.svg)](https://hub.docker.com/r/funcman/115pc/)


## 拉取镜像

budibase/budibase:latest


## 使用说明

拉取镜像
```shell
docker pull budibase/budibase:latest
```

启动容器
```shell
docker run -d -t \
  --name=budibase \
  -p 10000:80 \
  -v /local/path/data:/data \
  --restart unless-stopped \
  budibase/budibase:latest
```

*启动之后，可通过 `http://<ip>:10000`进行访问*


## 参数

|名称               |说明                                  |
|:-                 |:-                                   |
|`CONTAINER_NAME`   |应用名称                      |
|`APP_PORT`         |指定暴露的端口                         |
|  JWT_SECRET: ${JWT_SECRET}          |  |
|  MINIO_ACCESS_KEY: ${MINIO_KEY}     | |
|  MINIO_SECRET_KEY: ${MINIO_SECRET}  | |
|  REDIS_PASSWORD: ${REDIS_PASS}      | |
|  COUCHDB_USER: ${DB_USER}           | |
|  COUCHDB_PASSWORD: ${DB_PASS}       |  |    
|  INTERNAL_API_KEY: ${INTERNAL_API_KEY}  |  |



## 注意事项



## 感谢


