# xray-frontend-package-public

这是公开的带面板安装包仓，只放带 Web 面板版本的后端安装包和校验文件。

## 仓库定位

| 仓库 | 类型 | 用途 |
| --- | --- | --- |
| `xray-frontend-source` | 私有源码仓 | 修改带 Web 面板的前端、后端、安装脚本和打包逻辑 |
| `xray-frontend-package-public` | 公开包仓 | 下载带 Web 面板的安装包 |
| `xray-headless-source` | 私有源码仓 | 修改无前端版本源码 |
| `xray-release-public` | 公开包仓 | 下载无前端版本安装包 |

## 当前内容

- `xray-backend-release.tar.gz`
  - 最新带 Web 面板后端安装包
- `SHA256SUMS.txt`
  - 安装包 SHA256 校验文件

这里不放源码，不放 Android、Windows 或其它客户端成品。客户端文件如果需要发布，应使用单独的客户端发布仓或清晰命名的专用目录，避免和带面板服务端安装包混在一起。

## 对应源码仓

- [`huotian420-cyber/xray-frontend-source`](https://github.com/huotian420-cyber/xray-frontend-source)

## 下载

```bash
curl -fL --progress-bar -o xray-backend-release.tar.gz https://raw.githubusercontent.com/huotian420-cyber/xray-frontend-package-public/main/xray-backend-release.tar.gz
curl -fL --progress-bar -o SHA256SUMS.txt https://raw.githubusercontent.com/huotian420-cyber/xray-frontend-package-public/main/SHA256SUMS.txt
sha256sum -c SHA256SUMS.txt
```

## 覆盖升级

```bash
sudo bash -c 'set -e; apt-get update -y; apt-get install -y curl tar; workdir=$(mktemp -d); cd "$workdir"; curl -fL --progress-bar -o xray-backend-release.tar.gz https://raw.githubusercontent.com/huotian420-cyber/xray-frontend-package-public/main/xray-backend-release.tar.gz; curl -fL --progress-bar -o SHA256SUMS.txt https://raw.githubusercontent.com/huotian420-cyber/xray-frontend-package-public/main/SHA256SUMS.txt; sha256sum -c SHA256SUMS.txt; tar -xzf xray-backend-release.tar.gz; chmod +x install.sh; ./install.sh upgrade'
```

## 全新安装

```bash
sudo bash -c 'set -e; apt-get update -y; apt-get install -y curl tar; workdir=$(mktemp -d); cd "$workdir"; curl -fL --progress-bar -o xray-backend-release.tar.gz https://raw.githubusercontent.com/huotian420-cyber/xray-frontend-package-public/main/xray-backend-release.tar.gz; curl -fL --progress-bar -o SHA256SUMS.txt https://raw.githubusercontent.com/huotian420-cyber/xray-frontend-package-public/main/SHA256SUMS.txt; sha256sum -c SHA256SUMS.txt; tar -xzf xray-backend-release.tar.gz; chmod +x install.sh; ./install.sh'
```

## 打包同步

在 `xray-frontend-source` 工作区执行：

```bash
PUBLIC_RELEASE_DIR=/path/to/xray-frontend-package-public bash backend/package-release.sh
```

脚本只应同步：

- `xray-backend-release.tar.gz`
- `SHA256SUMS.txt`
