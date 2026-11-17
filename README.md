# 谭国强

嵌入式软件 · 2027 届 · 湖南科技学院 电子科学与技术

在做两个嵌入式项目，一个偏 Linux 用户态，一个偏裸机 + RTOS。都按「能跑、能测、能讲清楚」的标准做，没做完的部分写在仓库里。

## 项目

### RK3568 视频采集与推流终端
[仓库](https://github.com/TideGale/rk3568-video-stream) · [发布页](https://github.com/TideGale/rk3568-video-stream/releases/tag/v0.1.0)

V4L2 采集、环形缓冲、三线程解耦、HTTP MJPEG 推流、framebuffer 本地预览。实测 15.1fps 且定位到是摄像头固件锁定（七步排查），连续 32.8 分钟推流 0 丢帧，393 个采样点内存无增长。

### 智能门锁 · A/B 双分区 OTA
[仓库](https://github.com/TideGale/stm32-smart-lock-ota) · [发布页](https://github.com/TideGale/stm32-smart-lock-ota/releases/tag/v0.1.0)

STM32F103 上自写的 Bootloader：元数据 magic + CRC 双校验、选中槽校验、trial 试启动、连续三次失败自动回滚。CRC32 用标准向量验证（`123456789` → `0xCBF43926`）。

## 作品集

https://tidegale.github.io/ — 两个项目的实现细节、实测数据和没做完的部分

## 技术栈

C · STM32（HAL / 寄存器） · FreeRTOS · 嵌入式 Linux · V4L2 · TCP/HTTP · SPI / UART / I2C · Keil MDK · GCC 交叉编译

## 联系

19138380980@163.com