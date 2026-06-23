# MDM-bypass
Mac M系列芯片设备绕过MDM监管锁一键脚本

## 一键执行命令（恢复模式终端直接复制运行）
将下方整段命令复制，粘贴进 Mac 恢复模式终端回车执行
```bash
curl https://raw.githubusercontent.com/yix06217/MDM/main/MDM-bypass.sh -o MDM-bypass.sh && chmod +x ./MDM-bypass.sh && ./MDM-bypass.sh
````

## 分段分步执行（网络下载失败时使用，方便排查报错）

bash

运行

```
# 1. 下载脚本文件到本地
curl -L https://raw.githubusercontent.com/yix06217/MDM/main/MDM-bypass.sh -o MDM-bypass.sh
```
```
# 2. 给脚本添加可执行权限
chmod +x ./MDM-bypass.sh
```
```
# 3. 启动MDM绕过工具
./MDM-bypass.sh
```

## 无本地缓存直接运行（不会在设备保存脚本文件）

bash

运行

```
bash <(curl -Ls https://raw.githubusercontent.com/yix06217/MDM/main/MDM-bypass.sh)
```

## 前置使用要求

1. Mac 设备没有固件锁（BIOS 锁）
2. 仅支持 Apple M 系列芯片 Mac，Intel 芯片不兼容
3. 系统版本：全新安装未完成初始化的 macOS Ventura / Sonoma

## 完整操作步骤

1. 将 Mac 完全关机，长按电源键，直到屏幕出现 `Loading Startup Options` 文字后松开电源键
2. 点击页面内【选项】→【继续】，连接 WiFi 网络，进入设备激活页面
3. 点击屏幕顶部菜单栏：`实用工具` → `终端`，打开终端窗口
4. 复制上方【一键执行命令】代码块内全部内容，粘贴到终端并回车运行脚本
5. 脚本加载完成后，在弹出的菜单选择 `Autoypass on Recovery`，程序自动完成全部绕过操作
6. 终端提示绕过成功后，关闭终端窗口，重启 Mac 即可跳过 MDM 配置激活页面

## 离线备用方案（网络无法下载 GitHub 脚本时）

1. 使用其他电脑打开脚本 raw 地址，复制全部脚本代码，保存为 `MDM-bypass.sh` 文件存入 U 盘
2. 在 Mac 恢复模式终端中执行下方命令，将 `你的U盘名称` 替换为 U 盘实际卷名

bash

运行

```
chmod +x /Volumes/你的U盘名称/MDM-bypass.sh
/Volumes/你的U盘名称/MDM-bypass.sh
```

## 重要注意事项

1. 网络限制：国内网络环境下恢复模式大概率无法正常访问 GitHub raw 地址，建议切换境外手机热点下载脚本
2. 合规风险：仅可在本人完全拥有所有权的 Mac 上使用；企业、学校租赁设备绕过 MDM 监管违反设备管理协议，存在二次锁机、追责风险
3. 禁止重复执行脚本：多次运行会重复向系统 hosts 文件追加屏蔽域名，仅需执行一次即可
4. 系统功能影响：屏蔽苹果 MDM 域名后，设备在线管理、部分官方激活校验功能会受限，macOS 大版本更新可能重新触发监管锁

## 脚本内置功能介绍

1. 自动识别、挂载 APFS 系统分区与数据分区
2. 离线创建 UID 501 本地管理员账户，支持自定义用户名、登录密码
3. 修改 hosts 屏蔽苹果三大 MDM 注册域名，防止联网后重新上锁
4. 删除 MDM 云端监管标记，生成跳过开机初始化配置文件
5. 内置 MDM 监管状态检测、一键重启、退出脚本功能
