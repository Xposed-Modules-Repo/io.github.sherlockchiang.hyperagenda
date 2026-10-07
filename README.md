# 锁屏日程 / HyperAgenda

一个面向 **Xiaomi HyperOS 4** 的 LSPosed 模块，在系统锁屏时钟下方显示本地日历中接下来的日程。

此仓库用于 LSPosed 模块分发，只存放模块说明与 Release。源码与问题反馈请前往 [SherlockChiang/HyperAgenda](https://github.com/SherlockChiang/HyperAgenda)。

## 下载

[下载最新 Release](https://github.com/Xposed-Modules-Repo/io.github.sherlockchiang.hyperagenda/releases/latest)

包名：`io.github.sherlockchiang.hyperagenda`

## 功能

- 默认显示下一条日程：上排名称，下排相对时间与地点；可设置显示 1–3 条。
- 相对时间提示，如「10 分钟后」「进行中 · 还剩 25 分钟」「明天 09:30」。
- 按系统日历分组筛选，可选择显示或隐藏哪些日历。
- 提供完整信息、隐藏地点、只提示有日程等隐私选项。
- 可选点击后通过系统解锁流程打开小米日历对应事件。
- 可调整未来范围与距时钟间距，文字与位置跟随原生锁屏。

## 安装

前置条件：已 Root、已安装可用的 LSPosed、Xiaomi HyperOS 4。

1. 下载并安装 APK，打开应用授予日历读取权限。
2. 在 LSPosed 中启用「锁屏日程」。
3. 作用域只勾选 **系统界面（`com.android.systemui`）**。
4. 重启系统界面或手机，在应用中检查注入状态并配置日历分组。

## 旧版迁移

0.6.2 起包名由 `com.vince.hyperagenda` 改为 `io.github.sherlockchiang.hyperagenda`。
新包名会作为独立应用安装，不能覆盖旧应用，设置不会自动迁移。

请先停用旧模块并记录设置，再安装、授权和启用新版。确认新版正常后可卸载旧应用。
**不要同时启用两个版本**，以免重复注入日程。

## 隐私

日程来自 Android 系统日历 Provider，只申请日历读取权限，没有网络权限。
锁屏隐私过滤在应用进程完成，被隐藏的标题与地点不会传给 SystemUI。

「认证后显示详情」目前的行为是：设备设有安全锁时仅提示有日程；没有安全锁时显示详情。

## 兼容与反馈

当前适配目标为 HyperOS 4；其他 ROM 或 SystemUI 版本未作兼容承诺。
系统更新可能改变锁屏实现。若无法显示，先检查日历权限、所选日历、显示范围和 LSPosed 作用域。

[提交问题](https://github.com/SherlockChiang/HyperAgenda/issues)时，请附手机型号、完整系统版本、SystemUI 版本及包含 `HyperAgenda` 的 LSPosed 日志。
日志中若含个人日程信息，请先去除。

---

HyperAgenda displays upcoming local calendar events on the Xiaomi HyperOS 4 lockscreen.
Recommended scope: `com.android.systemui`. Source code and support: [SherlockChiang/HyperAgenda](https://github.com/SherlockChiang/HyperAgenda).
