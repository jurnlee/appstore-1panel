# SFTPGo

SFTPGo 是一款功能齐全、高度可配置化、支持自定义 HTTP/S，FTP/S 和 WebDAV 的 SFTP 服务。

> 支持的后端存储：本地文件系统、加密本地文件系统、S3（兼容）对象存储，Google Cloud 存储，Azure Blob 存储，SFTP。

## 主要功能：

### 多用户支持

SFTPGo 允许您创建和管理多个用户帐户，每个用户都可以有自己的独立访问权限和目录。

### 高度可配置

您可以根据自己的需求进行广泛的配置，包括用户访问控制、文件上传和下载限制、身份验证方法等。

### 安全性

SFTPGo 支持多种身份验证方法，包括SSH密钥、用户名/密码和多因素身份验证。它还支持IP白名单和黑名单，以增强安全性。

### 文件传输管理

用户可以使用 SFTP 和 SCP 协议安全地上传和下载文件。SFTPGo 提供了传输速率限制、文件夹配额和文件类型过滤等功能。

### 高性能

SFTPGo 高度优化，能够处理大量的并发连接和高吞吐量的文件传输。

### 监控和日志

SFTPGo 提供了详细的日志记录和监控功能，以便管理员跟踪用户活动和服务器性能。

### 自动化

通过 REST API 和 Webhook 支持，SFTPGo 可以集成到您的自动化工作流程中，从而实现更高效的文件传输管理。

### 可扩展性

您可以通过插件和扩展来增加 SFTPGo 的功能，以满足特定需求。

## 版本说明

+ `version` 纯版本号
  这是事实上的镜像，它基于 Debian，可在 debian 官方镜像中找到。如果您不确定自己的需求是什么，您可能想使用这个。

+ `-alpine` Alpine Linux
  该映像基于流行的 Alpine Linux 项目，可在 alpine 官方映像中获取。 Alpine Linux 比大多数发行版基础镜像 (~5MB)
  小得多，因此通常会导致镜像更薄。

+ `-distroless` Distroless `尚未发布`
  该图像基于流行的 Distroless 项目。我们使用最新的基于 Debian 的 distroless 镜像作为基础。
  变体仅包含静态链接的 sftpgo 二进制文件及其最小的运行时依赖项，因此它不允许 shell 访问（未安装 shell）。 SQLite
  支持被禁用，因为它需要 CGO，因此未安装 C 运行时。默认数据提供程序是 bolt ，除 sqlite 之外的所有受支持的数据提供程序都可以工作。我们仅提供精简版本，因此可选的
  git 依赖项不可用。

+ `-slim` Slim
  该图像基于流行的 Slim 项目。我们使用最新的基于 Debian 的 slim 镜像作为基础。这些标签提供了一个更精简的映像，不包含 jq
  以及可选的 git 和 rsync 依赖项。

+ `-plugins` Plugins
  这些标签提供了标准图像以及 /usr/local/bin 中安装的所有“官方”插件。

+ `edge` Edge `尚未发布`
  这些标签提供了最新的开发版本，可能包含未经测试的功能和 bug。它们不适合生产环境。