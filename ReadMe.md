# 说明

本分支为个人修改版，原版代码请查看main分支。

原版说明如下：

- [readme_cn]( project/readme_cn.txt)
- [readme_en]( project/readme_en.txt)

## 编译

简易编译步骤如下：

- 配置目标（需要支持的主板）：

  ```bash
  ./build.sh lunch
  ```

  

- 编译：

  ```bash
  ./build.sh
  ```


编译过程中缺少什么就安装什么。

编译完成后镜像文件所在目录为output/image,可使用SocToolKit工具打开此目录进行烧录。

# 烧录

SocToolKit在[tools](tools)目录下。

根据所使用的操作系统选择使用linux还是windows目录。

注意：由于Linux下的工具未使用静态链接，可能存在glibc兼容问题。

简易烧录步骤如下：

- 打开SocToolKit，根据板子类型，选择芯片为RV1103或RV1106。
- 使用SocToolKit打开编译完成后的镜像目录。
- 按住BOOT按键（此时确保芯片未上电），使用USB连接PC机并上电。此步骤的主要目的为进入maskrom模式。
- 开始烧录等待写入完成。

# 调试

基于Linux的开发板调试方式多种多样，如串口调试、网络调试（ssh、基于TCP的adb等）、USB调试（基于USB的adb、使用USB虚拟网卡进行网络调试等）。

本人主要使用串口调试， 串口为UART2,115200 8N1。

注意：调试串口在Linux下的设备名为/dev/ttyFIQ0，而非/dev/ttyS2。



