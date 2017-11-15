# FFmpegInAndroid
该项目编译了可以在 **Android** 平台下使用的 **FFmpeg**



## 项目结构
* 根目录ffmpeg-3.2.5是交叉编译后的源码目录，用于cMake编译时候寻找头文件
* 根目录ffmpeg-script包含FFmpeg、libx264 、fdk-aac源码以及编译脚本、编译后产物

## 2017-11-15 更新
* 添加压缩视频命令
* 添加日志系统，logcat上可以打印出c日志，方便调试
* ffmpeg-3.2.5集成libx264 、fdk-aac-0.1.5交叉编译精简版

## 编译
1. 首先确保安装配置了**NDK环境**。

2. 本项目是在**Windows** 环境下编译的，在根目录ffmpeg-script的buildoutput目录中可以找到**x264_arm_build.sh**、**fdkacc_arm_build.sh**、**ffmpeg_arm_build.sh**三个脚本，分别编译x264 fdkacc 然后交叉编译ffmpeg，其中的lib目录下便是编译后产物目录。以上三个脚本只支持armv7（其他架构同理修改脚本CPU=armv7-a/x86...），交叉编译脚本ffmpeg_arm_build.sh编译的是**精简版的SO 库**。

3. 如果你自己用该脚本编译，请注意修改每个脚本中的**NDK**指向你自己的环境，如果是**Ubuntu**或者**Mac**你需要把**darwin-x86_64** 的字样修改为 **linux-x86_64**。


## 注意事项
* 不同版本的ffmpeg编译后可能有点小区别，本项目基于ffmpeg-3.2.5

