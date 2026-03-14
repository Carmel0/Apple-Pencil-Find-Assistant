# Apple Pencil 找回助手 (Apple Pencil Find Assistant)

## 📢 软件声明
本软件纯免费！禁止任何形式的售卖。
作者小红书 ID: **1557442523**

## 📖 简介
这是一个专为 iPadOS 打造的系统日志分析工具，运行于 iSH (Alpine Linux) 环境。它能通过分析 sysdiagnose 诊断包，精准捕获 Apple Pencil 的 **Lost (信号丢失)** 和 **Found (重新发现)** 事件，帮助您通过时间线找回丢失的爱笔。

## 📂 诊断包获取方式
在使用本工具前，您需要先从 iPad 获取 sysdiagnose 诊断文件：
1. **官方教程**：请查看 [Apple 官方支持文档](https://support.apple.com/zh-cn/guide/platform-support/supd3f43814e/web)。
2. **图文教程**：也可前往作者小红书首页（ID: 1557442523）查看相关笔记。

## 📁 准备工作 (关键步骤)
1. **保存文件**：生成 sysdiagnose 后，请将其分享并保存到 iPad 的 **“文件 (Files)”** 应用中（建议直接存放在“我的 iPad”根目录或“下载”文件夹）。
   - **文件名样例**：`sysdiagnose_2026.03.14_14-57-07+0800_iPhone-OS_iPad_23D8133.tar.gz`
2. **挂载到 iSH**：
   在 iSH 中运行以下命令来访问 iPad 的系统文件夹：
   ```bash
   mkdir -p /mnt/ipad
   mount -t ios dummy /mnt/ipad
   ```
   *执行后会弹出 iOS 系统文件选择器，请选择包含诊断包的文件夹并点击右上角的“打开”或“完成”。*

## 🚀 iSH 一键安装与使用
在 iPad 的 iSH 终端中直接复制并运行以下指令：
```bash
# 下载并解压工具 (以 v1.1 为例)
wget https://github.com/Carmel0/Apple-Pencil-Find-Assistant/releases/download/v1.1/pencil_analyzer-v1.1.tar.gz && \
tar -zxf pencil_analyzer-v1.1.tar.gz && \
cd pencil_analyzer-v1.1-release/ && \
chmod +x pencil_analyzer

# 运行分析 (假设诊断包在挂载点根目录)
./pencil_analyzer /mnt/ipad/sysdiagnose_你的文件名.tar.gz
```

## 💡 找回指引
- 运行分析后，请重点关注最后一次 **Lost** 但是没有后续 **Found** 的记录时间。
- 根据该时间点回忆您当时的活动范围，即为笔的大致丢失位置。

## ☕ 赞赏与支持
如果有帮到找回可以到小红书置顶笔记收藏或留言，或者到支付宝 **carmel0@me.com** 赞赏请喝柠檬茶。🍋
祝您早日找回爱笔！
