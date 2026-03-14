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

## 🚀 iSH 一键安装与使用
在 iPad 的 iSH 终端中直接复制并运行以下指令：
```bash
wget https://github.com/Carmel0/Apple-Pencil-Find-Assistant/releases/download/v1.0/pencil_analyzer-v1.0.tar.gz && \
tar -zxf pencil_analyzer-v1.0.tar.gz && \
chmod +x pencil_analyzer && \
./pencil_analyzer [您的诊断包路径.tar.gz]
```

## 💡 找回指引
- 运行分析后，请重点关注最后一次 **Lost** 但是没有后续 **Found** 的记录时间。
- 根据该时间点回忆您当时的活动范围，即为笔的大致丢失位置。

## ☕ 赞赏与支持
如果有帮到找回可以到小红书置顶笔记收藏或留言，或者到支付宝 **carmel0@me.com** 赞赏请喝柠檬茶。🍋
祝您早日找回爱笔！
