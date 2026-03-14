# Apple Pencil 找回助手 (Apple Pencil Find Assistant)

## 📢 软件声明
本软件纯免费！禁止任何形式的售卖。
作者小红书 ID: **1557442523**

## 📖 简介
这是一个专为 iPadOS 打造的系统日志分析工具，运行于 iSH (Alpine Linux) 环境。
1. **找笔神器**：利用 sysdiagnose 锁定笔最近离开 iPad 磁吸范围的时间，帮助精准推断丢笔地点。
2. **电池管家**：自动捕获 iPad 电池循环次数与最大容量百分比，方便评估维修需求。

## 📂 诊断包获取方式
在使用本工具前，您需要先从 iPad 获取 sysdiagnose 诊断文件：
1. **官方教程**：请查看 [Apple 官方支持文档](https://support.apple.com/zh-cn/guide/platform-support/supd3f43814e/web)。
2. **图文教程**：也可前往作者小红书首页（ID: 1557442523）查看相关笔记。

## 📁 准备工作 (关键步骤)

### 1. 系统要求
- **已验证系统**：已在 **iPadOS 17.3** 及 **iPadOS 26.3** 上实测通过。
- **早期系统**：其他早期系统理论上兼容，但建议手动使用 Mac “控制台”应用作为备选。

### 2. 配置 iSH 环境 (初次使用必做)
在 iSH 终端中运行以下命令安装必要组件：
```bash
apk update
apk add wget tar ca-certificates
```

### 3. 保存并挂载诊断文件
将生成的 sysdiagnose 保存到 iPad 的 **“文件”** 应用中，然后在 iSH 中运行：
```bash
mkdir -p /mnt/ipad
mount -t ios dummy /mnt/ipad
```
*执行后选择包含诊断包的文件夹。*

## 🚀 iSH 一键安装与使用
在 iSH 终端中直接复制并运行以下指令：
```bash
# 下载并解压工具 (v5.5)
wget https://github.com/Carmel0/Apple-Pencil-Find-Assistant/releases/download/v5.5/pencil_analyzer-v5.5.tar.gz && \
tar -zxf pencil_analyzer-v5.5.tar.gz && \
cd pencil_analyzer-release/ && \
chmod +x pencil_analyzer

# 运行分析 (假设诊断包在挂载点根目录)
./pencil_analyzer /mnt/ipad/你的文件名.tar.gz
```

## 💡 找回指引
- **最强证据**：最强证据是 **Lost** 时间与最后一次 **RSSI** 骤降同步，且 **最后物理连接时间** 与 **Lost** 时间重合，之后再无 **Found** 记录。此时间点即为笔离开连接范围的精确时刻。

## ☕ 赞赏与支持
如果有帮到找回可以到小红书置顶笔记收藏或留言，或者到支付宝 **carmel0@me.com** 赞赏请喝柠檬茶。🍋
祝您早日找回爱笔！
