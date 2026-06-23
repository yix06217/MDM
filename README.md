# MDM-bypass
A one-click script to bypass MDM lock for Apple M-series Mac.

## One-Click Execute Command (Copy & Run directly in Recovery Terminal)
```bash
curl https://raw.githubusercontent.com/yix06217/MDM/main/MDM-bypass.sh -o MDM-bypass.sh && chmod +x ./MDM-bypass.sh && ./MDM-bypass.sh
Step-by-Step Command (For network troubleshooting)
bash
运行
# Download script
curl -L https://raw.githubusercontent.com/yix06217/MDM/main/MDM-bypass.sh -o MDM-bypass.sh
# Grant execute permission
chmod +x ./MDM-bypass.sh
# Launch bypass tool
./MDM-bypass.sh
Run without saving script locally
bash
运行
bash <(curl -Ls https://raw.githubusercontent.com/yix06217/MDM/main/MDM-bypass.sh)
Prerequisites
No firmware lock on your Mac
Only support Apple M-series chips
Fresh installed macOS Ventura / Sonoma (unfinished setup)
Full Operation Guide
Shut down Mac completely, hold power button until Loading Startup Options shows up, then release.
Click Options → Continue, connect WiFi to enter activation page.
Top menu bar: Utilities → Terminal.
Copy the one-click command above, paste into terminal and press Enter.
Select Autoypass on Recovery in script menu, auto finish bypass process.
Close terminal after success prompt, reboot Mac to skip MDM setup screen.
Offline Solution (If curl download failed)
Copy full script code from raw link on another computer, save as MDM-bypass.sh to USB drive.
Run this command in recovery terminal, replace YourUSBName with real USB volume name:
bash
运行
chmod +x /Volumes/YourUSBName/MDM-bypass.sh
/Volumes/YourUSBName/MDM-bypass.sh
Important Notes
Network issue: Domestic network cannot access GitHub raw link stably, use overseas mobile hotspot.
Compliance risk: Only use on Mac you fully own. Bypass company/school leased device MDM will violate management agreement.
Do NOT run script multiple times, it will duplicate block rules in hosts file.
After bypass, some Apple official online verification features will be limited, macOS major update may trigger MDM lock again.
Script Features
Auto detect & mount APFS System / Data volume
Offline create UID 501 admin user with custom username & password
Block Apple MDM domains via hosts file to prevent re-lock
Remove MDM cloud enrollment records, skip welcome setup
Built-in MDM enrollment check, reboot & exit function
plaintext

## 使用说明
1. 全选上面从 `# MDM-bypass` 到最后一行 `5. Built-in MDM enrollment check, reboot & exit function` 的全部内容；
2. 直接粘贴到你仓库的 `README.md`；
3. GitHub 自带代码块右上角复制图标，点开页面每个 ```bash 代码框都自带一键复制按钮，无需额外标签/折叠代码，是 GitHub 官方标准格式；
4. 链接已适配你的仓库 `yix06217/MDM`，无需修改。

### 极简独立一键复制区块（单独提取，可插在文档顶部）
```markdown
### Quick One-Click Command
```bash
curl https://raw.githubusercontent.com/yix06217/MDM/main/MDM-bypass.sh -o MDM-bypass.sh 
