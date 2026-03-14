# Apple Pencil Find Assistant

[中文说明 (Chinese Version)](README_CN.md)

## 📢 Software Statement
This software is completely FREE! Any form of selling is strictly prohibited.
Author Redbook (小红书) ID: **1557442523**

## 📖 Introduction
A professional system log analysis tool for iPadOS, running in the iSH (Alpine Linux) environment.
1. **Pencil Tracker**: Utilizes sysdiagnose to pinpoint exactly when the Pencil left the magnetic range, helping you infer the location of loss.
2. **Battery Health**: Automatically captures iPad battery cycle count and maximum capacity percentage for maintenance reference.

## 📂 How to get sysdiagnose
Before using this tool, you need to obtain a sysdiagnose file from your iPad:
1. **Official Guide**: Refer to the [Apple Support Document](https://support.apple.com/zh-cn/guide/platform-support/supd3f43814e/web).
2. **Visual Tutorial**: Visit the author's Redbook homepage (ID: 1557442523) for detailed notes.

## 📁 Preparation (Crucial Steps)

### 1. System Requirements
- **Verified Systems**: Tested and verified on **iPadOS 17.3** and **iPadOS 26.3**.
- **Legacy Systems**: Theoretically compatible with older versions. Manual analysis via macOS "Console" is recommended as a backup.

### 2. Setup iSH Environment (First-time users)
Run the following commands in your iSH terminal:
```bash
apk update
apk add wget tar ca-certificates
```

### 3. Mount Sysdiagnose
Save sysdiagnose to the **"Files"** app, then run in iSH:
```bash
mkdir -p /mnt/ipad
mount -t ios dummy /mnt/ipad
```
*Select the folder containing your diagnostic package.*

## 🚀 iSH Installation & Usage
Copy and run the following command in your iSH terminal:
```bash
# Download and extract the tool (v5.5)
wget https://github.com/Carmel0/Apple-Pencil-Find-Assistant/releases/download/v5.5/pencil_analyzer-v5.5.tar.gz && \
tar -zxf pencil_analyzer-v5.5.tar.gz && \
cd pencil_analyzer-release/ && \
chmod +x pencil_analyzer

# Run analysis
./pencil_analyzer /mnt/ipad/sysdiagnose_YOUR_FILENAME.tar.gz
```

## 💡 Finding Guidance
- **Strongest Evidence**: The strongest evidence of loss is when a **Lost** event coincides with a high absolute **RSSI** or matches the **Last Physical Conn** time, with no subsequent **Found** events.

## ☕ Support the Author
If this tool helped you, please consider liking/commenting on my Redbook pinned post, or send a "Lemon Tea" tip to Alipay: **carmel0@me.com**. 🍋
Good luck finding your Pencil!
