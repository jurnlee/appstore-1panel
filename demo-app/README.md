# Demo

[![Docker Automated build](https://img.shields.io/docker/automated/jlesage/baseimage-gui.svg)](https://hub.docker.com/r/funcman/115pc/)


## 拉取镜像



## 使用说明

拉取镜像
```shell
docker pull demo:1.0.0
```

启动容器
```shell
docker run -d --name=drawdb  -p 808:80  --restart=always  demo:1.0.0
```

*启动之后，可通过 `http://<ip>:808`进行访问*


## 参数

|名称               |说明                                  |
|:-                 |:-                                   |
|`CONTAINER_NAME`   |应用名称                      |
|`APP_PORT`         |指定暴露的端口                         |




## 注意事项



## 感谢


