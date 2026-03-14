# Apple Pencil 找回助手 (Apple Pencil Find Assistant)

## 📢 软件声明
本软件纯免费！禁止任何形式的售卖。
作者小红书 ID: **1557442523**

## 📖 简介
这是一个专为 **iPadOS 26.3+** 打造的系统日志 analysis 工具，运行于 iSH (Alpine Linux) 环境。它能通过分析 sysdiagnose 诊断包，精准捕获 Apple Pencil 的 **Lost (信号丢失)** 和 **Found (重新发现)** 事件，帮助您通过时间线找回丢失的爱笔。

> **注意**：本工具针对较新版本的 iPadOS 进行了优化。对于更早期的系统，日志结构可能不同，建议手动连接 Mac 使用“控制台”应用进行分析。

## 📂 诊断包获取方式
在使用本工具前，您需要先从 iPad 获取 sysdiagnose 诊断文件：
1. **官方教程**：请查看 [Apple 官方支持文档](https://support.apple.com/zh-cn/guide/platform-support/supd3f43814e/web)。
2. **图文教程**：也可前往作者小红书首页（ID: 1557442523）查看相关笔记。

## 📁 准备工作 (关键步骤)

### 1. 配置 iSH 环境 (初次使用必做)
在 iSH 终端中运行以下命令安装必要组件：
```bash
apk update
apk add wget tar ca-certificates
```

### 2. 保存诊断文件
生成 sysdiagnose 后，请将其分享并保存到 iPad 的 **“文件 (Files)”** 应用中（建议直接存放在“我的 iPad”根目录或“下载”文件夹）。
- **文件名样例**：`sysdiagnose_2026.03.14_14-57-07+0800_iPhone-OS_iPad_23D8133.tar.gz`

### 3. 挂载到 iSH
运行以下命令来访问 iPad 的系统文件夹：
```bash
mkdir -p /mnt/ipad
mount -t ios dummy /mnt/ipad
```
*执行后会弹出 iOS 系统文件选择器，请选择包含诊断包的文件夹并点击右上角的“打开”或“完成”。*

## 🚀 iSH 一键安装与使用
在 iPad 的 iSH 终端中直接复制并运行以下指令：
```bash
# 下载并解压工具 (以 v3.2 为例)
wget https://github.com/Carmel0/Apple-Pencil-Find-Assistant/releases/download/v3.2/pencil_analyzer-v3.2.tar.gz && \
tar -zxf pencil_analyzer-v3.2.tar.gz && \
cd pencil_analyzer-release/ && \
chmod +x pencil_analyzer

# 运行分析 (假设诊断包在挂载点根目录)
./pencil_analyzer /mnt/ipad/sysdiagnose_你的文件名.tar.gz
```

## 💡 找回指引
- 运行分析后，请重点关注最后一次 **Lost** 但是没有后续 **Found** 的记录时间。
- **最强证据**：最强证据是 Lost 时间与最后一次 RSSI 骤降同步，且最后物理连接时间与 Lost 时间重合，之后再无 Found 记录。此时间点即为笔离开连接范围的精确时刻。

## ☕ 赞赏与支持
如果有帮到找回可以到小红书置顶笔记收藏或留言，或者到支付宝 **carmel0@me.com** 赞赏请喝柠檬茶。🍋
祝您早日找回爱笔！
