# Drawdb
[![Docker Automated build](https://img.shields.io/docker/automated/jlesage/baseimage-gui.svg)](https://hub.docker.com/r/funcman/115pc/)


## 拉取镜像

```shell
docker pull registry.cn-hangzhou.aliyuncs.com/jlee/drawdb:1.0.0
```


## 创建容器

```shell
docker run -d --name=drawdb  -p 808:80  --restart=always  registry.cn-hangzhou.aliyuncs.com/jlee/drawdb:1.0.0
```

*启动之后，可通过 `http://<ip>:808`进行访问*


## 参数

|名称               |说明                                  |
|:-                 |:-                                   |
|`CONTAINER_NAME`         |应用名称，默认：drawdb                 |
|`APP_PORT`         |指定暴露的端口                         |




## 注意事项



## 感谢

* [jlesage/baseimage-gui](https://hub.docker.com/r/jlesage/baseimage-gui)提供的X图形应用容器基础镜像，使用它可以轻松将Linux图形应用程序以Web和VNC的方式使用。
