# FRAME 0.1.1

[FRAME 官网](https://leolucks.github.io/frame-web/official/) · [网页版](https://leolucks.github.io/frame-web/) · [Android 下载](https://github.com/leoLucks/frame-web/releases/download/v0.1.1/FRAME-0.1.1-android.apk)

- 新增 FRAME 产品官网与统一下载入口
- Android 支持联网检查版本、下载进度与安装包校验
- 校验包名、版本与签名后，由 Android 系统确认安装

现有 0.1.0 需先手动覆盖安装 0.1.1；之后可在 App 的「偏好与存储 → 版本更新」中检查、下载更新。安装最终由 Android 系统确认，下载校验失败会停止安装。

APK：FRAME-0.1.1-android.apk（16601401 字节），SHA-256：`8d28a2743ebf5b3bc853993cb7a2b30fdc2c10c4d3f2eac6100379ab5c2c8474`

网页：FRAME-0.1.1-web.zip，SHA-256：`e2d54c9aace05dc6aea20108c627c35d18ee849b4856aa25c4f12d317332243b`

安装包签名与 0.1.0 一致，当前仍沿用开发签名。Android 端的下载和系统安装交互尚待真机验收。iOS 尚无已签名安装包；相机传图、遥控与私人云创同步仍在完善和验证中。

## 发布与更新服务

此公开仓库仅存放编译产物、安装包分片和 Pages 工作流，原 App 工程源码保持私有。

官网与 App 共用 [stable.json](https://leolucks.github.io/frame-web/updates/stable.json) 版本清单。工作流在发布完整安装包并校验公开云创 API 后上线网页和版本清单。已有版本附件只核对、不覆盖。

后续发布需递增 package.json 的 version 与 frameVersionCode，沿用同一 Android 签名，重新构建后运行 prepare-public-release。完整安装包由 Actions 从两个分片重建，用户下载 Release 中的完整 APK。
