# Demo

[![Docker Automated build](https://img.shields.io/docker/automated/jlesage/baseimage-gui.svg)](https://hub.docker.com/r/funcman/115pc/)




## 快速部署

```shell
docker run \
  --name tooljet \
  --restart unless-stopped \
  -p 8080:80 \
  -e PORT=8080 \
  --platform linux/amd64 \
  -v tooljet_data:/var/lib/postgresql/13/main \
  tooljet/try:ee-lts-latest
```


*启动之后，可通过 `http://<ip>:8080`进行访问*


## 参数

|名称               |说明                                  |
|:-                 |:-                                   |
|`CONTAINER_NAME`   |应用名称                      |
|`APP_PORT`         |指定暴露的端口                         |




## 注意事项



## 感谢


