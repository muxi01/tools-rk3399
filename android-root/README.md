# 一、获取android的root权限
## 1.1想办法进入loader模式或者Maskrom模式
### 方案一：
- 1、开机键 + 音量-  【*】
- 2、开机键 + 音量+
### 方案二：
	1.adb reboot bootloader
	2.adb reboot recovery -->选择进入bootloader
## 1.2获取分区信息 [适合于当前机器] <也可以在linux下执行rkdeveloptool.bin pgpt>
- 1.WIN系统中打开<RKDevTool.exe> 【*】
- 2.Maskrom模式： 
Advanced Function -->Bboot -->下载rk3399_loader_v1.30.130.bin -->进入loader模式
- 3.Loader模式: 【*】
	Dev Parttion 获取boot.img 分区信息 

## 1.3在ubuntu中提取boot.img固件  【*】
- 1. rkdeveloptool.bin rl 0x1c000 0x10000 rk3399.boot.img 读取分区中boot.img文件

## 1.4 使用magisk修补boot.img 获得magisk_patched-30400_T5khH.img 【*】
- 1.安卓手机安装Magisk工具 
- 2.安装-->选择并修补一个文件-->boot.img--->开始
- 3.获得magisk_patched-30400_T5khH.img 文件

## 1.5 将修补后的magisk_patched-30400_T5khH.img 文件写入到boot.img分区地址 【*】
- 1.按照1.1/1.2方法进入loader模式
- 2.新建分区，填入分区地址，名称，文件路径
- 3.执行run

## 1.6 ADB获取root权限
- 1.设置-->开发者选项-->开发者模式-->USB调试 【*】
- 2.安装Launcher:
	adb push xxx /sdcard/
	adb shell 'pm install /sdcar/xxx'
- 3.adb shell 
- 4. su  #magisk工具会提示安装magisk工具包，需要从github下载二进制文件，需要外网


# 二、工具
存放路径为release
