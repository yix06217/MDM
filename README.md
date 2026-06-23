# MDM-bypass
Mac M系列芯片设备离线绕过MDM监管锁一键脚本

## 一键执行命令（恢复模式终端直接复制整条运行）
```bash
curl https://raw.githubusercontent.com/yix06217/MDM/main/MDM-bypass.sh -o MDM-bypass.sh && chmod +x ./MDM-bypass.sh && ./MDM-bypass.sh
分段分步执行（网络异常时推荐，方便排查报错）
bash
运行
# 1. 下载脚本文件
curl -L https://raw.githubusercontent.com/yix06217/MDM/main/MDM-bypass.sh -o MDM-bypass.sh
# 2. 添加可执行权限
chmod +x ./MDM-bypass.sh
# 3. 启动绕过工具
./MDM-bypass.sh
无本地缓存直接管道运行（不保存脚本到设备）
bash
运行
bash <(curl -Ls https://raw.githubusercontent.com/yix06217/MDM/main/MDM-bypass.sh)
前置要求 Prerequisites
设备无固件锁（BIOS 锁）
仅支持 Apple M 系列芯片 Mac
系统版本：macOS Ventura / Sonoma 全新安装未完成初始化
完整操作流程
完全关机 Mac，长按电源键，直到屏幕出现 Loading Startup Options 再松开按键
点击【选项】→【继续】，连接 WiFi 进入设备激活界面
顶部菜单栏打开：实用工具 → 终端
复制上方一键执行命令粘贴到终端，回车运行脚本
在弹出菜单选择 Autoypass on Recovery，自动完成全部绕过操作
脚本提示成功后关闭终端，重启 Mac，即可跳过 MDM 配置页面
离线备用方案（网络无法下载脚本时）
其他电脑打开脚本 raw 地址，复制全部代码保存为 MDM-bypass.sh 存入 U 盘
恢复模式终端挂载 U 盘后执行以下命令，替换「你的 U 盘名称」为实际 U 盘卷名
bash
运行
chmod +x /Volumes/你的U盘名称/MDM-bypass.sh
/Volumes/你的U盘名称/MDM-bypass.sh
重要注意事项
网络限制：国内网络环境下恢复模式大概率无法访问 GitHub raw 地址，推荐切换境外手机热点下载脚本
设备合规：仅可在本人完全拥有所有权的 Mac 上使用；企业 / 学校租赁设备绕过 MDM 违反管理协议，存在二次锁机、追责风险
重复执行副作用：脚本多次运行会重复向 /etc/hosts 追加屏蔽域名，仅需执行一次即可
系统影响：屏蔽苹果 MDM 域名后，系统在线设备管理、部分官方激活校验功能会受限，系统大版本更新可能重新触发监管锁
脚本功能说明
自动识别并挂载 APFS 系统分区、数据分区
离线创建 UID 501 本地管理员账户，自定义用户名 / 密码
修改 hosts 屏蔽苹果三大 MDM 注册域名，防止联网重新上锁
删除 MDM 云端监管标记，生成跳过开机初始化配置文件
附带 MDM 监管状态检测、一键重启、退出功能
plaintext

## GitHub 一键复制组件（可直接放进README，自带复制按钮）
### 单行一键命令复制块
````markdown
<details>
<summary>点击展开复制一键执行完整命令</summary>

```bash
curl https://raw.githubusercontent.com/yix06217/MDM/main/MDM-bypass.sh -o MDM-bypass.sh && chmod +x ./MDM-bypass.sh && ./MDM-bypass.sh
</details> ````
