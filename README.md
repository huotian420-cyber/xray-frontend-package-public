# xray-frontend-package-public

这是公开的带前端成品仓。

当前保留的仓库关系：

| 仓库 | 类型 | 用途 |
| --- | --- | --- |
| `xray-frontend-source` | 私有源码仓 | 面板与后端源码 |
| `xray-frontend-package-public` | 公开包仓 | 带前端安装包与客户端成品 |
| `xray-headless-source` | 私有源码仓 | 无前端源码 |
| `xray-release-public` | 公开包仓 | 无前端安装包 |

## 当前内容

- 根目录 `xray-backend-release.tar.gz`
  - 最新带前端后端安装包
- 根目录 `SHA256SUMS.txt`
  - 根目录安装包校验
- `releases/android-20260427/`
  - Android 客户端 APK、构建清单、校验文件
- `releases/windows-20260427/`
  - Windows 客户端 ZIP、构建清单、校验文件

对应源码仓：

- [`huotian420-cyber/xray-frontend-source`](https://github.com/huotian420-cyber/xray-frontend-source)
- 当前同步源码提交：`4c532e1`

## 直接下载

```bash
curl -fL --progress-bar -o xray-backend-release.tar.gz https://raw.githubusercontent.com/huotian420-cyber/xray-frontend-package-public/main/xray-backend-release.tar.gz
curl -fL --progress-bar -o SHA256SUMS.txt https://raw.githubusercontent.com/huotian420-cyber/xray-frontend-package-public/main/SHA256SUMS.txt
grep "xray-backend-release.tar.gz" SHA256SUMS.txt | sha256sum -c -
```

## 仓库内客户端成品

- `releases/android-20260427/v2rayNG_2.1.3-fdroid_arm64-v8a.apk`
- `releases/android-20260427/v2rayNG_2.1.3-fdroid_universal.apk`
- `releases/windows-20260427/v2rayN-windows-64.zip`

## 覆盖升级

```bash
sudo bash -c 'set -e; apt-get update -y; apt-get install -y curl tar; workdir=$(mktemp -d); cd "$workdir"; curl -fL --progress-bar -o xray-backend-release.tar.gz https://raw.githubusercontent.com/huotian420-cyber/xray-frontend-package-public/main/xray-backend-release.tar.gz; tar -xzf xray-backend-release.tar.gz; chmod +x install.sh; ./install.sh upgrade'
```

## 全新安装

```bash
sudo bash -c 'set -e; apt-get update -y; apt-get install -y curl tar; workdir=$(mktemp -d); cd "$workdir"; curl -fL --progress-bar -o xray-backend-release.tar.gz https://raw.githubusercontent.com/huotian420-cyber/xray-frontend-package-public/main/xray-backend-release.tar.gz; tar -xzf xray-backend-release.tar.gz; chmod +x install.sh; ./install.sh'
```
