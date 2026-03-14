# Apple Pencil Find Assistant

[中文说明 (Chinese Version)](README_CN.md)

## 📢 Software Statement
This software is completely FREE! Any form of selling is strictly prohibited.
Author Redbook (小红书) ID: **1557442523**

## 📖 Introduction
This is a system log analysis tool specifically designed for **iPadOS 26.3+**, running in the iSH (Alpine Linux) environment. By analyzing sysdiagnose packages, it accurately captures Apple Pencil **Lost** and **Found** events, helping you locate your lost Pencil through a precise timeline.

> **Note**: This tool is optimized for newer iPadOS versions. For older systems, the log structure may differ, and we recommend manual analysis using the macOS Console app.

## 📂 How to get sysdiagnose
Before using this tool, you need to obtain a sysdiagnose file from your iPad:
1. **Official Guide**: Refer to the [Apple Support Document](https://support.apple.com/zh-cn/guide/platform-support/supd3f43814e/web).
2. **Visual Tutorial**: Visit the author's Redbook homepage (ID: 1557442523) for detailed notes.

## 📁 Preparation (Crucial Steps)

### 1. Setup iSH Environment (First-time users)
Run the following commands in your iSH terminal to install required components:
```bash
apk update
apk add wget tar ca-certificates
```

### 2. Save Sysdiagnose File
After generating sysdiagnose, share and save it to the iPad **"Files"** app (recommended in the root of "On My iPad" or "Downloads").
- **Filename Example**: `sysdiagnose_2026.03.14_14-57-07+0800_iPhone-OS_iPad_23D8133.tar.gz`

### 3. Mount in iSH
Run the following commands in iSH to access iPad system folders:
```bash
mkdir -p /mnt/ipad
mount -t ios dummy /mnt/ipad
```
*A file picker will appear. Select the folder containing your sysdiagnose and tap "Open" or "Done".*

## 🚀 iSH Installation & Usage
Copy and run the following command in your iSH terminal:
```bash
# Download and extract the tool (v3.2)
wget https://github.com/Carmel0/Apple-Pencil-Find-Assistant/releases/download/v3.2/pencil_analyzer-v3.2.tar.gz && \
tar -zxf pencil_analyzer-v3.2.tar.gz && \
cd pencil_analyzer-release/ && \
chmod +x pencil_analyzer

# Run analysis (assuming sysdiagnose is in the mount root)
./pencil_analyzer /mnt/ipad/sysdiagnose_YOUR_FILENAME.tar.gz
```

## 💡 Finding Guidance
- After running the analysis, focus on the timestamp of the last **Lost** event that does NOT have a subsequent **Found** event.
- **Strongest Evidence**: The strongest evidence of loss is when a Lost event coincides with a high absolute RSSI or matches the Last Physical Conn time, with no subsequent Found events.

## ☕ Support the Author
If this tool helped you, please consider liking or leaving a message on my Redbook pinned post, or send a "Lemon Tea" tip to Alipay: **carmel0@me.com**. 🍋
Good luck finding your Pencil!
