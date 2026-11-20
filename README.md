# 谭国强

嵌入式软件 · 2027 届 · 湖南科技学院 电子科学与技术

手上有两个嵌入式项目，一个 Linux 用户态，一个裸机加 RTOS。都按「能跑、能测、能讲清楚」在做，没做完的部分写在仓库里，不藏。

## 项目

### RK3568 视频采集与推流终端
[仓库](https://github.com/TideGale/rk3568-video-stream) · [发布页](https://github.com/TideGale/rk3568-video-stream/releases/tag/v2.1-tts)

V4L2 采集、环形缓冲、三线程解耦、HTTP MJPEG 推流、framebuffer 本地预览。实测 15.1fps，查了七步才确认是摄像头固件锁的，不是代码。连续跑 32.8 分钟，推流 0 丢帧，393 个采样点内存没涨。

v2.0 加了语音层。常开录音，ALSA 采集，门限 900 才落盘。然后云端 ASR，说「拍一张」就抓帧，问「桌上有什么」就让模型看图回答，最后 TTS 念出来。端侧只走数据通路，本地模型 A55 四核跑不动，这是主动取舍。

### 智能门锁 · A/B 双分区 OTA
[仓库](https://github.com/TideGale/stm32-smart-lock-ota) · [发布页](https://github.com/TideGale/stm32-smart-lock-ota/releases/tag/v1.0)

STM32F103 上自写的 Bootloader：元数据 magic 加 CRC 双校验、选中槽校验、trial 试启动、连续三次失败自动回滚。CRC32 用标准向量验证过（`123456789` → `0xCBF43926`）。

v1.0 收尾了。A→B→A 双镜像闭环、坏包连续三次回滚、MQTT 远程开锁，三项都实测通过。

## 作品集

https://tidegale.github.io/ — 两个项目的实现细节、实测数据和没做完的部分

## 技术栈

C · STM32（HAL / 寄存器） · FreeRTOS · 嵌入式 Linux · V4L2 · TCP/HTTP · SPI / UART / I2C · Keil MDK · GCC 交叉编译

## 联系

19138380980@163.com