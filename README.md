本仓库修改自：https://github.com/lgs2007m/uboot-ipq60xx-build

u-boot-2016 源代码基于：https://github.com/gl-inet/uboot-ipq60xx

## 适配设备

此 U-Boot 适配以下 IPQ60xx eMMC 机型：

- 京东云太乙（RE-CS-07）
- 京东云亚瑟（RE-SS-01）
- 京东云雅典娜（RE-CS-02）
- 红米 AX5 JDCloud（RA50）

## 编译步骤

### 本地编译

```bash
# 编译环境：Ubuntu
# mbn 脚本使用 python3 运行，请安装并切换到 python3
sudo apt update
sudo apt install -y python3
sudo apt install -y build-essential device-tree-compiler
git clone https://github.com/chenxin527/uboot-ipq60xx-emmc-build.git
cd uboot-ipq60xx-emmc-build
./build.sh
```

### 云编译

Fork 本仓库后使用 GitHub Actions 云编译。

## 文件说明

编译生成的 U-Boot 文件：./uboot-ipq60xx-emmc.bin

因为 U-Boot 文件大小超过了 640KB，而京东云太乙、京东云亚瑟、京东云雅典娜、红米 AX5 JDCloud 等 IPQ60xx eMMC 机型的 0:APPSBL 分区大小只有 640KB，所以若要刷写此 U-Boot，请先扩容 0:APPSBL 分区。[点击此处](http://example.com) 获取分区教程及相关文件。

U-Boot 截图示例（[点击此处](./screenshots.md) 查看所有网页截图）：

![uboot-index-page](./screenshots/uboot-index-page.png)

## 网址说明

| 功能        | 网址                            | 备注                                |
| :---------- | :----------------------------- | :--------------------------------- |
| 更新固件     | http://192.168.1.1             | 支持内核大小为 6MB 和 12MB 的固件更新 |
| 更新 ART    | http://192.168.1.1/art.html    | 包含路由器网卡 MAC 地址及无线校准数据 |
| 更新 CDT    | http://192.168.1.1/cdt.html    | CDT 文件不得小于 10KB（10240 Bytes） |
| 更新 IMG    | http://192.168.1.1/img.html    | 可更新 GPT 分区表或者 EMMC IMG 镜像 |
| 更新 U-Boot | http://192.168.1.1/uboot.html  | 最大支持 1024KB（1048576 Bytes）的 U-Boot |
| 启动 uImage | http://192.168.1.1/uimage.html | Initramfs uImage，可直接上传至内存并启动 |

> [!NOTE]
>
> 因 U-Boot HTTP 服务器限制，不支持上传 10KB（10240 Bytes）以下的文件。若要上传的文件不足 10KB，请使用十六进制编辑器在文件末尾填充空数据（0x0），但不要超过其所在分区大小。此 U-Boot 支持上传的所有文件中，只有 CDT 文件有效数据不足 10KB，特此说明。

> [!TIP]
>
> uImage (U-Boot Image) 即所谓 “内存固件”。在 USB 9008 救砖模式下，利用 “启动 uImage” 功能可上传并启动临时 OpenWrt 固件，在临时固件中可使用预置的各种工具进行备份分区、救砖恢复等操作。
>
> [点击此处](http://example.com) 获取 USB 9008 救砖教程及相关文件。
>
> [点击此处](http://example.com) 获取经测试可正常使用的 uImage。
