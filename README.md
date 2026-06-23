方案 1：分步骤下载 + 执行（推荐，出问题可查看脚本内容）
bash
运行
# 1. 下载脚本到本地
curl -L https://raw.githubusercontent.com/yix06217/MDM/main/MDM-bypass.sh -o MDM-bypass.sh
# 2. 赋予运行权限
chmod +x ./MDM-bypass.sh
# 3. 启动脚本
./MDM-bypass.sh
方案 2：一键整条复制执行（和你截图 README 格式一致）
bash
运行
curl https://raw.githubusercontent.com/yix06217/MDM/main/MDM-bypass.sh -o MDM-bypass.sh && chmod +x ./MDM-bypass.sh && ./MDM-bypass.sh
方案 3：管道直接运行，不保存本地文件（极简）
bash
运行
bash <(curl -Ls https://raw.githubusercontent.com/yix06217/MDM/main/MDM-bypass.sh)
二、完整操作步骤（M 系列 Mac 跳过 MDM 配置流程）
关机，长按电源键直到出现「Loading Startup Options」，松开电源
点击选项 → 继续，连接 WiFi 联网激活页面
顶部菜单栏：实用工具 → 终端
复制上面【方案 2】整条命令粘贴到终端回车运行
菜单选择 Autoypass on Recovery 自动完成绕过 MDM、新建管理员、屏蔽监管域名
执行完成后退出终端，重启 Mac 即可跳过设备配置锁
三、关键注意事项
网络问题：Recovery 环境国内访问raw.githubusercontent.com大概率超时，会下载失败；解决办法：
切换手机热点（境外运营商网络成功率更高）
或者手动把脚本存 U 盘，在终端读取本地 U 盘脚本执行
设备限制：脚本仅支持 M 系列芯片 Mac，不支持 Intel；且不能有固件锁（BIOS 锁）
合规风险：仅在你完全拥有所有权的 Mac 上使用；公司 / 学校租赁设备绕过 MDM 违反设备管理协议，存在追责、二次锁机风险
重复执行副作用：多次运行会重复追加 hosts 屏蔽域名，建议仅执行一次即可
四、下载失败备用方案（离线运行）
如果 curl 无法联网下载：
正常电脑打开脚本 raw 链接，复制全部代码保存为 MDM-bypass.sh 放到 U 盘
Mac 恢复模式打开终端，挂载 U 盘后执行：
bash
运行
chmod +x /Volumes/你的U盘名称/MDM-bypass.sh
/Volumes/你的U盘名称/MDM-bypass.sh
