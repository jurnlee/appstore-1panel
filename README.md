 中文 | [English](./README-en.md)
***

## 目录
- [目录](#目录)
- [免责声明](#免责声明)
  - [镜像容器适配](#镜像容器适配)
  - [法律遵守](#法律遵守)
  - [免责声明接受](#免责声明接受)
- [1. 简介](#1-简介)
- [2. 使用方式](#2-使用方式)
  - [2.1 国内网络](#21-国内网络)
    - [2.1.1 使用 git 命令获取应用](#211-使用-git-命令获取应用)
    - [2.1.2 使用压缩包方式获取应用](#212-使用压缩包方式获取应用)
  - [2.2 国际互联网络](#22-国际互联网络)
    - [2.2.1 使用 git 命令获取应用](#221-使用-git-命令获取应用)
    - [2.2.2 使用压缩包方式获取应用](#222-使用压缩包方式获取应用)
  - [2.3 使用脚本安装更新](#23-使用脚本安装更新)
- [3. 备注](#3-备注)
- [4. 应用](#4-应用)
- [5. 常见问题](#5-常见问题)
  - [升级失败](#升级失败)
    - [解决方案：](#解决方案)

***

## 免责声明

### 镜像容器适配
本项目仅针对原`docker`镜像容器运行进行针对`1Panel`应用商店的适配。我们不对任何原始镜像的有效性做出任何明示或暗示的保证或声明，并且不对使用本仓库应用所造成的任何影响负责。用户在使用本项目时应自行承担风险。

### 法律遵守
用户在使用本仓库时必须遵守所在国家与地区的法律法规。某些应用可能受到特定国家法律的限制，用户需自行了解并遵守相关法律要求。本仓库不对用户违反法律法规所产生的任何后果负责。

### 免责声明接受
用户在导入本仓库并使用其中的应用时，即表示用户已经阅读、理解并同意接受本免责声明的所有条款和条件。

请注意，本免责声明仅针对本仓库的使用情况，并不包括其他第三方应用或服务。对于与本仓库链接的第三方内容，我们不对其准确性、完整性、可靠性或合法性负责。如果您在使用过程中遇到问题，请查看应用的官方文档或社区。

在使用本仓库之前，请确保已经阅读、理解并接受了本免责声明的所有条款和条件。

***
## 1. 简介
这是一些适配`1Panel`商店`2.0`版本的docker应用配置。

致力于一键运行各种 Docker 应用。无需复杂配置，享受便利和高效。

## 2. 使用方式

默认`1Panel`安装在`/opt/`路径下，如果不是按需修改以下。

### 2.1 国内网络

> GitHub加速方式
>> - https://mirror.ghproxy.com

#### 2.1.1 使用 git 命令获取应用

`1Panel`计划任务类型`Shell 脚本`的计划任务框里，添加并执行以下命令，或者终端运行以下命令，
```shell
git clone -b localApps https://mirror.ghproxy.com/https://github.com/okxlin/appstore /opt/1panel/resource/apps/local/appstore-localApps

cp -rf /opt/1panel/resource/apps/local/appstore-localApps/apps/* /opt/1panel/resource/apps/local/

rm -rf /opt/1panel/resource/apps/local/appstore-localApps
```

然后应用商店刷新本地应用即可。

#### 2.1.2 使用压缩包方式获取应用

`1Panel`计划任务类型`Shell 脚本`的计划任务框里，添加并执行以下命令，或者终端运行以下命令，
```shell
wget -P /opt/1panel/resource/apps/local https://mirror.ghproxy.com/https://github.com/okxlin/appstore/archive/refs/heads/localApps.zip

unzip -o -d /opt/1panel/resource/apps/local/ /opt/1panel/resource/apps/local/localApps.zip

cp -rf /opt/1panel/resource/apps/local/appstore-localApps/apps/* /opt/1panel/resource/apps/local/

rm -rf /opt/1panel/resource/apps/local/appstore-localApps

rm -rf /opt/1panel/resource/apps/local/localApps.zip
```

然后应用商店刷新本地应用即可。

### 2.2 国际互联网络

#### 2.2.1 使用 git 命令获取应用

`1Panel`计划任务类型`Shell 脚本`的计划任务框里，添加并执行以下命令，或者终端运行以下命令，
```shell
git clone -b localApps https://github.com/okxlin/appstore /opt/1panel/resource/apps/local/appstore-localApps

cp -rf /opt/1panel/resource/apps/local/appstore-localApps/apps/* /opt/1panel/resource/apps/local/

rm -rf /opt/1panel/resource/apps/local/appstore-localApps
```

然后应用商店刷新本地应用即可。

#### 2.2.2 使用压缩包方式获取应用

`1Panel`计划任务类型`Shell 脚本`的计划任务框里，添加并执行以下命令，或者终端运行以下命令，
```shell
wget -P /opt/1panel/resource/apps/local https://github.com/okxlin/appstore/archive/refs/heads/localApps.zip

unzip -o -d /opt/1panel/resource/apps/local/ /opt/1panel/resource/apps/local/localApps.zip

cp -rf /opt/1panel/resource/apps/local/appstore-localApps/apps/* /opt/1panel/resource/apps/local/

rm -rf /opt/1panel/resource/apps/local/appstore-localApps

rm -rf /opt/1panel/resource/apps/local/localApps.zip
```

然后应用商店刷新本地应用即可。


### 2.3 使用脚本安装更新


温馨提示：当您同时安装其他第三方库时，如果存在目录冲突，脚本会主动删除冲突的第三方库应用，如果您不同意，请不要执行脚本。我们建议您在安装之前备份您的数据，或手动安装。

> 方案一：使用 `curl` 安装，不会提示脚本下载异常

```shell
#!/bin/bash

# 定义脚本URL
script_url="https://github.com/jurnlee/appstore-1panel/releases/download/install/install.sh"

# 执行脚本
echo "Downloading and executing script from $script_url..."
bash <(curl -sL "$script_url")

# 输出执行结果
echo "Script execution completed."

```

+ Tip 如果你只看到两行命令,说明执行失败

```sh
Downloading and executing script from https://github.com/junrlee/appstore-1panel/releases/download/install/install.sh...
Script execution completed.
```

+ 给脚本配置网络代理 （插入到定义脚本URL之前即可）

```sh
# 定义代理服务器地址和端口
proxy_server="server address"
proxy_port="server port"
# 设置网络代理
export http_proxy="http://$proxy_server:$proxy_port"
export https_proxy="http://$proxy_server:$proxy_port"
```

当前使用 `http` 代理，如果你的代理服务器是 `socks5` 请修改 `http_proxy` 和 `https_proxy` 为 `socks5` 协议

> 方案二：复制 `install.sh` 脚本内容

[install.sh](install.sh)

## 3. 备注

**未显示在本地应用列表里的，表示未完全适配应用商店面板操作**

**但是支持直接终端运行。**

> 本仓库应用基本支持直接 `docker-compose up` 运行

以`rustdesk`为例

```shell
# 进入 rustdesk 的最新版本目录
cd /opt/1panel/resource/apps/local/rustdesk/versions/latest/

# 复制 .env.sample 为 .env
cp .env.sample .env

# 编辑 .env 文件，修改参数
nano .env

# 启动 RustDesk
docker-compose up -d

# 查看连接所需密钥
cat ./data/hbbs/id_ed25519.pub

```

## 4. 应用

- [x] [drawdb](https://github.com/drawdb-io/drawdb)
- [x] [Elastic](https://www.elastic.co/)
    - [x] [Elasticsearch](https://www.elastic.co/elasticsearch/)
    - [x] [Kibana](https://www.elastic.co/kibana/)
    - [ ] [Logstash](https://www.elastic.co/logstash/)
- [x] [Emby](https://emby.media/)
- [x] [Gitea](https://gitea.io/)
    - [ ] [Gogs](https://gogs.io/)
- [x] [Jellyfin](https://jellyfin.org/)
- [x] [Minio](https://min.io/)
- [x] [MySQL](https://www.mysql.com/)
    - [x] [MariaDB](https://mariadb.org/)
    - [ ] [Percona](https://www.percona.com/)
- [x] [Nacos](https://nacos.io/)
- [x] [OneDev](https://onedev.io/)
- [x] [SftpGo](https://sftpgo.com/)
- [x] [SpeedTest](https://www.speedtest.net/)
    - [x] [SpeedTest-X](https://github.com/BadApple9/speedtest-x/)
- [x] [SpeedTest-Tracker](https://docs.speedtest-tracker.dev/)
- [x] [Transmission](https://transmissionbt.com/)
- [x] [ZeroTier](https://www.zerotier.com/) `客户端`
    - [x] [Ztncui](https://www.zerotier.com/) `服务端`


## 5. 常见问题

### 升级失败

请检查您的网络是否正常
请检查您的磁盘空间是否充足

#### 解决方案：

卸载重装

- 备份参数，记录软件安装参数
- 卸载软件
- 再次安装升级版本
- 填写之前保留参数
- 安装成功
  历史数据问题：由于使用持久化目录，卸载软件不会删除数据，请不要误删持久化目录，默认为 `/home/data/{appname}`
