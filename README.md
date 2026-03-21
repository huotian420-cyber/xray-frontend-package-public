# xray-frontend-release-public

这是 **公开的带前端安装包仓库**。

你需要这样理解它：
- 这里只放 **带前端 / 面板版** 安装包
- 仓库根目录始终保留当前最新的带前端包
- 用它来直接下载可访问网页面板的版本

它 **不是**：
- 无前端安装包仓
- 私有源码仓

当前文件：
- `xray-backend-release.tar.gz`
- `SHA256SUMS.txt`

对应私有源码提交：
- `62978dd` `Fix Reality fallback mode-switch conflict`

仓库根目录直链：

```bash
curl -fL --progress-bar -o xray-backend-release.tar.gz https://raw.githubusercontent.com/huotian420-cyber/xray-frontend-release-public/main/xray-backend-release.tar.gz
```

和另外 3 个仓的关系：
- 带前端私有完整源码仓：
  - [huotian420-cyber/xray-](https://github.com/huotian420-cyber/xray-)
- 无前端私有源码仓：
  - [huotian420-cyber/xray-headless-source](https://github.com/huotian420-cyber/xray-headless-source)
- 公开无前端安装包仓：
  - [huotian420-cyber/xray-release-public](https://github.com/huotian420-cyber/xray-release-public)

说明：
- 这里是带前端公开包
- 如果你要改代码，不要看这个仓，去 `xray-`
- 如果你只要无前端 headless 包，不要下这个仓，去 `xray-release-public`
