# FRAME 0.1.6

[FRAME 官网](https://leolucks.github.io/frame-web/official/) · [网页版](https://leolucks.github.io/frame-web/) · [Android 下载](https://github.com/leoLucks/frame-web/releases/download/v0.1.6/FRAME-0.1.6-android.apk)

- 修正同一次蓝牙握手重复确认被误报为不匹配的问题
- 手机 Wi-Fi 使用智能设备入口，取消计算机配对流程
- 分离照片读取与控制权限，读到机型不再代表控制已授权
- 真实手机 Wi-Fi 失败原因仍需结合新版错误阶段继续确认
- 网页版新增 RAW 导入与在线调色工作台，支持曝光、白平衡、色温、色调、明暗与饱和度调整
- RAW 解码、预览与 JPEG 导出均在浏览器本地完成，不上传用户原片

现有 0.1.0 需先手动覆盖安装 0.1.6；之后可在 App 的「偏好与存储 → 版本更新」中检查、下载更新。安装最终由 Android 系统确认，下载校验失败会停止安装。

APK：FRAME-0.1.6-android.apk（16494489 字节），SHA-256：`092d4dfbaf3a3a7eaa8d27aa1646db08b215205411dc7abfe011ead10cdb1e5a`

网页（Pages 热修复包）：FRAME-0.1.6-web.zip，SHA-256：`5c249b249026329d85b39721763e530ceeb7239971308d0b41a25d00e8f02901`

安装包签名与 0.1.0 一致，当前仍沿用开发签名。Android 端的下载和系统安装交互尚待真机验收。iOS 尚无已签名安装包；相机传图、遥控与私人云创同步仍在完善和验证中。

## 发布与更新服务

此公开仓库仅存放编译产物、安装包分片和 Pages 工作流，原 App 工程源码保持私有。

官网与 App 共用 [stable.json](https://leolucks.github.io/frame-web/updates/stable.json) 版本清单。工作流在核对完整安装包并校验公开云创 API 后上线网页和版本清单。网页可在不改动既有 Android Release 附件的情况下发布 Pages 热修复。

后续发布需递增 package.json 的 version 与 frameVersionCode，沿用同一 Android 签名，重新构建后运行 prepare-public-release。完整安装包由 Actions 从两个分片重建，用户下载 Release 中的完整 APK。
