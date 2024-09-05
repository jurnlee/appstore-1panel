
# Spug

以下操作会创建一个用户名为 admin 密码为 spug.cc 的管理员账户，可自行替换管理员账户/密码。

`docker exec spug init_spug admin spug.cc``

## 简介

Spug：麻雀，麻雀虽小，五脏俱全。

Spug是面向中小型企业设计的轻量级无Agent的自动化运维平台，整合了主机管理、主机批量执行、主机在线终端、文件在线上传下载、应用发布部署、在线任务计划、配置中心、监控、报警等一系列功能。

## 特性

- 批量执行: 主机命令在线批量执行
- 在线终端: 主机支持浏览器在线终端登录
- 文件管理: 主机文件在线上传下载
- 任务计划: 灵活的在线任务计划
- 发布部署: 支持自定义发布部署流程
- 配置中心: 支持 KV、文本、json 等格式的配置
- 监控中心: 支持站点、端口、进程、自定义等监控
- 报警中心: 支持短信、邮件、钉钉、微信等报警方式
- 优雅美观: 基于 Ant Design 的 UI 界面
- 开源免费: 前后端代码完全开源

## 环境
Python 3.6及以上
Mysql 5.6及以上
Redis 3.x及以上
Nodejs 12.14 LTS

## 更新日志

详见： https://spug.cc/docs/change-log 

### 3.3.2
2023-11-29

🔧 优化升级依赖版本兼容性

### 3.3.1
2023-11-23

🔧 优化推送助手集成体验

### 3.3.0
2023-11-16

🌟 集成了推送助手，提供监控和任务的短信、电话告警支持 参考文档
🐞 修复主机列表弹框某些情况下未显示主机信息的问题 by @allwaysLove