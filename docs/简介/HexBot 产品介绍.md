## HEXBOT 简介

HEXBOT是一款多功能、高兼容开发板，采用六边形设计，统一接口，每个模块相互独立，可重复使用。

HEXBOT由主板、芯片、接口等组成。不同的功能模块内有不同的结构来支持相应的运行，包括：电机、舵机，超声波传感器，数码管LED屏幕等外设，且兼容STM32、ESP32、GD32等主芯片。

HEXBOT可覆盖大一计算机导论课程，大二使用FPGA的计算机组成原理实验，大三使用MCU的嵌入式系统实验，大四毕业设计等课程需求。**现已应用于武汉大学、武汉学院等高校**。

<center><img src="HEXBOT 产品介绍.assets/hexbot_7_modules.png" alt="hexbot_7_modules" style="zoom: 25%;" /></center>



## HEXBOT 产品构成

<center>

<!-- | 图片                                                         | 名称 | 数量 | 备注 |
| ------------------------------------------------------------ | ---- | ---- | ---- |
| <img src="HEXBOT 产品介绍.assets/hexbot_main2.2.1.png" alt="image-20220604155233724" style="zoom:50%;" /> | 主板 | 1 | STM32F103 |
| <img src="HEXBOT 产品介绍.assets/hexbot_7_modules.png" alt="image-20220604155241900" style="zoom:50%;" /> | 键盘 | 2 | 摇杆手柄、按键 |
| <img src="HEXBOT 产品介绍.assets/hexbot_7_modules.png" alt="image-20220604155247762" style="zoom:50%;" /> | 调试器 | 1 | —— |
| <img src="HEXBOT 产品介绍.assets/hexbot_7_modules.png" alt="image-20220604155252669" style="zoom:50%;" /> | 蓝牙 | 1 | 蓝牙5.0 |
| <img src="HEXBOT 产品介绍.assets/hexbot_7_modules.png" alt="image-20220604155258369" style="zoom:50%;" /> | 舵机 | 3 | SG90舵机 |
| <img src="HEXBOT 产品介绍.assets/hexbot_7_modules.png" alt="image-20220604155307671" style="zoom:50%;" /> | 数码管 | 1 | 0.56 inch 四位 |
| <img src="HEXBOT 产品介绍.assets/hexbot_7_modules.png" alt="image-20220604155320677" style="zoom:50%;" /> | OLED屏幕 | 1 | 0.96 inch |
| <img src="HEXBOT 产品介绍.assets/motor.png"  style="zoom: 33%;" /> | 减速电机 | 3 | 带编码器 |
| <img src="HEXBOT 产品介绍.assets/st-link.jpg"  style="zoom: 33%;" /> | 下载器 | 1 | ST-Link V2 | -->

</center>

<center>
    <font size="1" color="grey">HEXBOT完整套装列表</font>



---

## 文档简介

### STM32

1. STM32CubeIDE、STM32 Utility等工具的安装及使用，快速熟悉开发环境
2. 实验手册
   1. 裸机程序实验
      1. GPIO、IIC、SPI、CAN等接口及协议的原理讲解及示例代码
      2. 使用主芯片电路板驱动外部拓展模块的综合型物联网实验案例
   2. FreeRTOS实验
      1. FreeRTOS的内核代码讲解
      2. FreeRTOS的任务调度

### ESP32

1. 兼容Arduino的开发环境，可用图形化编程，快速入门代码编写
2. 丰富的物联网项目案例
3. MQTT、WIFI、蓝牙等通信协议的讲解及代码实现

### GD32

1. PlatformIO、Python、GCC等工具链的安装及应用
2. RISC-V架构的库函数开发

<img src="HEXBOT 产品介绍.assets/document.png"  style="zoom: 20%;" />

<center>
    <font size="1" color="grey">线上文档截图</font>



## 产品定制化服务

<br>

### PCB定制

可根据院校需求，提供定制化电路板服务。PCB上可印刷指定学校logo、文字标识。

<img src="HEXBOT 产品介绍.assets/hexbot_stm32_main_back.jpg" style="zoom: 15%;" />

<center>
    <font size="1" color="grey">HEXBOT主板丝印（以武汉大学为例）</font>

<br>


### 课程定制

可根据院校需求，提供定制化课程培训服务。

培训内容包括：

1. STM32嵌入式编程
2. ESP32物联网编程
3. GD32嵌入式编程
4. Altium Disgner 原理图、PCB绘制
5. 立创 EDA 原理图、PCB绘制
6. ……

| <img src="HEXBOT 产品介绍.assets/IMG_3350.HEIC.jpg"  style="zoom: 15%;" /> | <img src="HEXBOT 产品介绍.assets/IMG_3246.HEIC.jpg"  style="zoom:15%;" /> | <img src="HEXBOT 产品介绍.assets/IMG_3272.HEIC.jpg" style="zoom:15%;" /> |
| ----------------------------------------------------- | ---------------------------------------------------- | --------------------------------------------------- |

<center>
    <font size="1" color="grey">HEXBOT定制化课程培训（以武汉学院为例）</font>




