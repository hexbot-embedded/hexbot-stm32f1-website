# STM32CubeIDE

### 描述

STM32CubeIDE是一体式多操作系统开发工具，是STM32Cube软件生态系统的一部分。 

[![STM32CubeIde Board Photo](STM32CubeIDE.assets/image.PF267946.en.feature-description-include-personalized-no-cpn-medium.jpg)](https://www.st.com/zh/development-tools/stm32cubeide.html#)

STM32CubeIDE是一种高级C/C++开发平台，具有STM32微控制器和微处理器的外设配置、代码生成、代码编译和调试功能。它基于Eclipse®/CDT™框架和用于开发的GCC工具链，以及用于调试的GDB。它支持集成数以百计的现有插件，正是这些插件使Eclipse® IDE的功能趋于完整。
STM32CubeIDE集成了STM32CubeMX的STM32配置与项目创建功能，以便提供一体化工具体验，并节省安装与开发时间。在通过所选板卡或示例选择一个空的STM32 MCU或MPU，或者预配置微控制器或微处理器之后，将创建项目并生成初始化代码。在开发过程的任何时间，用户均可返回外设或中间件的初始化和配置阶段，并重新生成初始化代码，期间不会影响用户代码。
STM32CubeIDE包含相关构建和堆栈分析仪，能够为用户提供有关项目状态和内存要求的有用信息。
STM32CubeIDE还具有标准和高级调试功能，其中包括CPU内核寄存器、存储器和外设寄存器以及实时变量查看、串行线传输监测器接口或故障分析器的视图。

- ### 所有功能

  - 通过STM32CubeMX来集成服务：STM32微控制器、微处理器、开发平台和示例项目选择引脚排列、时钟、外设和中间件配置项目创建和初始化代码生成具有增强型STM32Cube扩展包的软件和中间件
  - 基于Eclipse®/CDT™，支持Eclipse®插件、GNU C/C++ for Arm®工具链和GDB调试器
  - STM32MP1 系列：支持OpenSTLinux项目：Linux支持Linux
  - 其他高级调试功能包括：CPU内核、外设寄存器和内存视图实时变量查看视图系统分析与实时跟踪(SWV)CPU故障分析工具支持RTOS感知调试，包括Azure
  - 支持ST-LINK（意法半导体）和J-Link (SEGGER)调试探头
  - 从Atollic® TrueSTUDIO®和AC6 System Workbench for STM32 (SW4STM32)导入项目
  - 支持多种操作系统：Windows®、Linux®和macOS®，仅限64位版本

  [
    ](https://www.st.com/zh/development-tools/stm32cubeide.html#)

## 1.1 STM32CubeIDE的下载

CubeIDE的官方下载地址：[https://www.st.com/zh/development-tools/stm32cubeide.html]()

在官网可以下载最新版本和更多版本。

![image-20220519140850932](img/image-20220519140850932.png)

点击“获取软件”。

![image-20220519140924600](img/image-20220519140924600.png)

然后根据自己的电脑系统进行选择并开始下载。

## 1.2 STM32CubeIDE的安装

在下载完成后，会在下载文件夹得到一个zip压缩包，解压后安装（注意，必须解压后安装，不能在压缩包中安装软件。）安装过程与普通软件安装过程相同。安装过程里，在选择组件窗口中，按照默认的勾选设置安装两个组件。

![image-20220519141306626](img/image-20220519141306626.png)

## 1.3 STM32CubeIDE的运行

安装完成后，运行STM32CubeIDE。

**设置汉字编码流程**：1.点击【窗口】，选择【首选项】<img src="../../../Downloads/Hexbot/typora-user-images/image-20220519142344386.png" alt="image-20220519142344386" style="zoom:50%;" /><img src="img/image-20220519142439745.png" alt="image-20220519142439745" style="zoom:33%;" />

2.展开【常规】选项，选择【工作空间】，选中【文本文件编码-其他】，点击输入“GBK”，点击【应用并关闭】。

![image-20220519142818108](img/image-20220519142818108.png)

## 1.4 创建项目：

1.选择菜单栏中【文件】选项，选择【新建】，选择【STM32 Project】。

![image-20220519144859775](img/image-20220519144859775.png)

2.在【Commercial Part Number】中输入芯片型号，并在右栏中进行选择，然后点击【下一步】。

![image-20220519145117971](img/image-20220519145117971.png)

3.输入项目名，并点击【完成】，即完成项目创建。

![image-20220519145311866](..\typora-user-images\image-20220519145311866.png)

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.
