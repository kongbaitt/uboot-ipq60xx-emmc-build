## 📋 更新日志

[点击此处](https://github.com/chenxin527/uboot-ipq60xx-emmc-build/blob/main/changelog.md) 查看完整更新日志。

### ✨ 功能更新

- 添加 bootconfig 命令，用于切换启动分区
- 添加 untar 命令，用于解析 sysupgrade tar image
- 支持刷写 sysupgrade 格式的固件
- 固件上传完成后检查其 kernel 与 rootfs 是否超过相应分区大小
- 支持通过 DHCP 为客户端分配 IP（dhcpd 跟随 httpd 自动启动）

### 📢 其他更新

- 调整文件上传完成后内存填充的起始地址，改用 0 填充内存
- 调整上传文件大小错误时打印的日志内容
- 合并 NN6000 V1 & V2 的 U-Boot
- 为打印的日志中的十六进制数添加 0x 前缀

## 📡 支持设备

- 京东云太乙（RE-CS-07）
- 京东云亚瑟（RE-SS-01）
- 京东云雅典娜（RE-CS-02）
- 连我 NN6000 V1
- 连我 NN6000 V2
- 红米 AX5 JDCloud（RA50）

## 📸 网页截图

[点击此处](https://github.com/chenxin527/uboot-ipq60xx-emmc-build/blob/bbcbeac8bf2d4df9714913b171d33a60a1e0be31/screenshots.md) 查看所有网页截图。

![uboot-index-page](https://github.com/chenxin527/uboot-ipq60xx-emmc-build/blob/42af5d1c143ea42dd02023db5bef45f56677674f/screenshots/uboot-index-page.png)
