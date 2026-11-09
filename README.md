# FRAME 0.1.0

[打开网页版](https://leolucks.github.io/frame-web/) · [版本说明与下载](https://github.com/leoLucks/frame-web/releases/tag/v0.1.0)

此公开仓库存放编译网页 ZIP、Android APK 的两个分片、校验文件及发布工作流。App 工程源代码保存在独立的私有仓库。

## 安装

[下载完整 Android 0.1.0 APK](https://github.com/leoLucks/frame-web/releases/download/v0.1.0/FRAME-0.1.0-android.apk)：`FRAME-0.1.0-android.apk`（16,433,091 字节）。仓库中的 `.part01` 与 `.part02` 由 Actions 合并，请直接安装 Release 中的完整 APK。

SHA-256：`f16db445f4c2562e23ce3c5d415c6855c14502a9e41848b22e22735e3d059a44`

iOS 尚未开放下载。Android 当前沿用 Android Debug 开发签名，后续应用商店分发需要发布签名。

## 功能范围

网页支持浏览器本地照片管理、13 款水印、六角度相机展示和公开云创方案。私人账户同步尚待真实账户验证；在线网页无法建立相机 TCP 会话。App 相机配对与控制待真机验收，相机传图与遥控拍摄尚未完整接通。

公开云创方案使用[独立只读 API](https://frame-public-cloud-api.leojames19970101.chatgpt.site/api/nikon/health)，不转发访问者的账户凭据。

## 发布与部署

`releases/v0.1.0/` 包含 `FRAME-0.1.0-web.zip`、`FRAME-0.1.0-android.apk.part01`、`FRAME-0.1.0-android.apk.part02` 和 `FRAME-0.1.0-android.apk.sha256`。每个 APK 分片不超过 8 MiB。

Settings → Pages → Source 选择 GitHub Actions。推送 main 或手动运行 Deploy FRAME website 后，工作流先校验分片和网页 ZIP，再合并并校验完整 APK；使用工作流默认 token 发布完整 APK、网页 ZIP 和校验文件到 v0.1.0 Release。已有同名附件会下载并逐字节核对，内容不同会停止发布。

网页 ZIP 的 SHA-256 为 `7b0d8d5308c0e1ad0873b187b7c5371bf0a1ecf4757ebb647bf226dd77066d14`。工作流解压仓库内的 ZIP，并检查公开 API 的 health GET、recipes POST 均返回 HTTP 200、精确 Pages Origin 的 CORS 头及非空方案列表；检查失败会阻止 Pages 部署。

详细功能范围与安装说明见 [RELEASE_NOTES.md](RELEASE_NOTES.md)。
