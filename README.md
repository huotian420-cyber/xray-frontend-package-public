# xray-frontend-package-public

这是现在在用的带前端包仓。

先看现在保留的 4 个仓：

| 仓库 | 前端 | Mihomo | 类型 | 现在用途 |
| --- | --- | --- | --- | --- |
| `xray-frontend-source` | 有 | 没有 | 源码仓 | 改带前端代码 |
| `xray-frontend-package-public` | 有 | 没有 | 包仓 | 下带前端安装包 |
| `xray-headless-source` | 没有 | 有 | 源码仓 | 改无前端代码 |
| `xray-release-public` | 没有 | 有 | 包仓 | 下无前端安装包 |

## 先记住这件事

- 现在真正要看的只有这 4 个仓
- 这个仓是“带前端 + 包仓”
- 以前的旧仓已经删掉，不用再看旧包仓名字

## 这个仓里是什么

- 带前端版本的安装包
- 没有 Mihomo 这条线
- 这里只放下载文件，不放源码

## 什么时候来这里

- 你要下载带前端版本
- 你只想拿安装包和校验文件

## 什么时候不要来这里

- 你要改源码
- 你要找无前端版本
- 你要找 Mihomo 那条无前端线

## 当前文件

- 安装包：`xray-backend-release.tar.gz`
- 校验文件：`SHA256SUMS.txt`
- 对应源码仓：[`huotian420-cyber/xray-frontend-source`](https://github.com/huotian420-cyber/xray-frontend-source)

## 下载

```bash
curl -fL --progress-bar -o xray-backend-release.tar.gz https://raw.githubusercontent.com/huotian420-cyber/xray-frontend-package-public/main/xray-backend-release.tar.gz
```

```bash
curl -fL --progress-bar -o SHA256SUMS.txt https://raw.githubusercontent.com/huotian420-cyber/xray-frontend-package-public/main/SHA256SUMS.txt
grep "xray-backend-release.tar.gz" SHA256SUMS.txt | sha256sum -c -
```

## 覆盖更新

保留原机器的 `data.db`、`config.conf`、Nginx、证书和防火墙，只覆盖后端程序与管理脚本：

```bash
sudo bash -c 'set -e; apt-get update -y; apt-get install -y curl tar; workdir=$(mktemp -d); cd "$workdir"; curl -fL --progress-bar -o xray-backend-release.tar.gz https://raw.githubusercontent.com/huotian420-cyber/xray-frontend-package-public/main/xray-backend-release.tar.gz; tar -xzf xray-backend-release.tar.gz; chmod +x install.sh; ./install.sh upgrade'
```

升级后如果博客还停留在旧状态，可以直接在服务器执行：

```bash
sudo xy blog-normal
```

## 全新安装

```bash
sudo bash -c 'set -e; apt-get update -y; apt-get install -y curl tar; workdir=$(mktemp -d); cd "$workdir"; curl -fL --progress-bar -o xray-backend-release.tar.gz https://raw.githubusercontent.com/huotian420-cyber/xray-frontend-package-public/main/xray-backend-release.tar.gz; tar -xzf xray-backend-release.tar.gz; chmod +x install.sh; ./install.sh'
```
