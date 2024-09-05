# Mindoc

Golang实现的基于beego框架的接口在线文档管理系统。

MinDoc 的前身是 SmartWiki 文档系统。SmartWiki 是基于 PHP 框架 laravel 开发的一款文档管理系统。因 PHP 的部署对普通用户来说太复杂，所以改用 Golang 开发。可以方便用户部署和实用。其功能和界面源于 kancloud 。

可以用来储存日常接口文档，数据库字典，手册说明等文档。内置项目管理，用户管理，权限管理等功能，能够满足大部分中小团队的文档管理需求。

## 构建
```shell
# 克隆源码
git clone https://github.com/mindoc-org/mindoc.git
# go包安装
go mod tidy -v
# 编译(sqlite需要CGO支持)
go build -ldflags "-w" -o mindoc main.go
# 数据库初始化(此步骤执行之前，需配置`conf/app.conf`)
./mindoc install
# 执行
./mindoc
# 开发阶段运行
bee run
```



## 使用说明

拉取镜像
```shell
docker pull registry.cn-hangzhou.aliyuncs.com/mindoc-org/mindoc:v2.1
```

参数   
DB_ADAPTER                  指定DB类型(默认为sqlite)
MYSQL_PORT_3306_TCP_ADDR    MySQL地址
MYSQL_PORT_3306_TCP_PORT    MySQL端口号
MYSQL_INSTANCE_NAME         MySQL数据库名称
MYSQL_USERNAME              MySQL账号
MYSQL_PASSWORD              MySQL密码
HTTP_PORT                   程序监听的端口号
MINDOC_ENABLE_EXPORT        开启导出(默认为false)


启动容器
```shell
docker run -p 8181:8181 --name mindoc -e DB_ADAPTER=mysql -e MYSQL_PORT_3306_TCP_ADDR=10.xxx.xxx.xxx -e MYSQL_PORT_3306_TCP_PORT=3306 -e MYSQL_INSTANCE_NAME=mindoc -e MYSQL_USERNAME=root -e MYSQL_PASSWORD=123456 -e httpport=8181 -d daocloud.io/lifei6671/mindoc:latest
```

*启动之后，可通过 `http://localhost:8181`进行访问*

                               |


## 注意事项



## 感谢


