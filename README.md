# xray-frontend-release-public

这是带前端安装包的公开发布仓。

## 仓库角色

- 可见性：`public`
- 内容：当前最新带前端安装包、校验文件、Release 历史版本
- 用途：直接下载可访问网页面板的安装包

## 不要拿它做什么

- 不要把它当源码仓
- 不要把它当无前端安装包仓

## 当前发布

- 包名：`xray-backend-release.tar.gz`
- 校验：`SHA256SUMS.txt`
- 对应源码仓：[`huotian420-cyber/xray-`](https://github.com/huotian420-cyber/xray-)
- 对应功能提交：`081b00d` `Add managed SSH port switching`
- 当前固定版本：`v2026.03.30-frontend-direct-2`

## Tag 规则

- 带前端公开包统一使用：
  - `vYYYY.MM.DD-frontend-direct-N`
- 例子：
  - `v2026.03.30-frontend-direct-2`
- 含义：
  - `YYYY.MM.DD`：发布日期
  - `frontend`：带前端安装包
  - `direct`：当前这条公开直发稳定线
  - `N`：当天递增版本号

## 本次版本包含

- 移除 SSH knock 前后端与安装脚本逻辑
- 接入真实流量统计链路
- 按 Xray 当前行为补齐 `XHTTP / gRPC / ALPN(h2/h3/http/1.1)` 兼容
- 新增 SSH 端口管理：可在菜单里输入目标端口，自动放行新端口、重载 SSH、关闭旧端口并同步 Fail2ban

## 下载

Ubuntu 一键安装最新版本：

```bash
sudo bash -c 'set -e; apt-get update -y; apt-get install -y curl tar; workdir=$(mktemp -d); cd "$workdir"; curl -fL --progress-bar -o xray-backend-release.tar.gz https://raw.githubusercontent.com/huotian420-cyber/xray-frontend-release-public/main/xray-backend-release.tar.gz; tar -xzf xray-backend-release.tar.gz; chmod +x install.sh; ./install.sh'
```

Ubuntu 一键安装固定版本：

```bash
sudo bash -c 'set -e; apt-get update -y; apt-get install -y curl tar; workdir=$(mktemp -d); cd "$workdir"; curl -fL --progress-bar -o xray-backend-release.tar.gz https://raw.githubusercontent.com/huotian420-cyber/xray-frontend-release-public/v2026.03.30-frontend-direct-2/xray-backend-release.tar.gz; tar -xzf xray-backend-release.tar.gz; chmod +x install.sh; ./install.sh'
```

最新版本：

```bash
curl -fL --progress-bar -o xray-backend-release.tar.gz https://raw.githubusercontent.com/huotian420-cyber/xray-frontend-release-public/main/xray-backend-release.tar.gz
```

固定版本：

```bash
curl -fL --progress-bar -o xray-backend-release.tar.gz https://raw.githubusercontent.com/huotian420-cyber/xray-frontend-release-public/v2026.03.30-frontend-direct-2/xray-backend-release.tar.gz
```

校验：

```bash
curl -fL --progress-bar -o SHA256SUMS.txt https://raw.githubusercontent.com/huotian420-cyber/xray-frontend-release-public/main/SHA256SUMS.txt
sha256sum -c SHA256SUMS.txt
```

## 4 个仓怎么分

- 带前端私有源码：[`huotian420-cyber/xray-`](https://github.com/huotian420-cyber/xray-)
- 无前端私有源码：[`huotian420-cyber/xray-headless-source`](https://github.com/huotian420-cyber/xray-headless-source)
- 带前端公开安装包：[`huotian420-cyber/xray-frontend-release-public`](https://github.com/huotian420-cyber/xray-frontend-release-public)
- 无前端公开安装包：[`huotian420-cyber/xray-release-public`](https://github.com/huotian420-cyber/xray-release-public)

## 如果你的目标不是下载包

- 要改代码：去 `xray-`
- 要下无前端包：去 `xray-release-public`
