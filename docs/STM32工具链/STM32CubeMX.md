# STM32CubeMX

### 描述

[STM32CubeMX](https://www.st.com/zh/development-tools/stm32cubemx.html) 是一种图形工具，通过分步过程可以非常轻松地配置STM32微控制器和微处理器，以及为Arm® Cortex®-M内核或面向Arm® Cortex®-A内核的特定Linux®设备树生成相应的初始化C代码。 STM32CubeMX board photo第一步包括选择与所需外设集匹配的意法半导体STM32微控制器、微处理器或开发平台，同时包括在特定开发平台上运行的示例。

对于微处理器，第二步允许配置GPIO和设置整个系统的时钟，并交互地将外设分配给Arm® Cortex®-M或Cortex®-A内核。特定实用工具（如DDR配置和微调）增强了STM32微处理器的易用性。对于Cortex®-M内核，配置包含了额外步骤，与微控制器的十分相似。

对于微控制器和微处理器Arm® Cortex®-M，第二步为通过引脚分配冲突处理器、时钟树设置助手、功耗计算器，以及用于配置外设（如GPIO或USART）和中间件栈（如USB或TCP/IP）的实用工具来配置各个必需的嵌入式软件。

借助增强型STM32Cube扩展包，可扩展默认软件和中间件栈。可直接通过STM32CubeMX中可用的专用包管理器，直接下载意法半导体或意法半导体合作伙伴提供的软件包，其他软件包可以从本地驱动器进行安装。

此外，STM32CubeMX中的独特实用程序STM32PackCreator可帮助开发人员构建自己的增强型STM32Cube扩展包。

最终，用户可以生成与所选配置匹配的软件包。这一步提供Arm® Cortex®-M初始化C代码（可随时用于多个开发环境），或面向Arm® Cortex®-A的部分Linux®设备树。

### 所有功能

- 直观的STM32微控制器和微处理器选择
- 丰富易用的图形用户界面，允许配置：
    -  支持自动冲突解决的引脚分配
    - 支持面向Arm® Cortex®-M内核带参数约束动态验证的外设和中间件功能模式
    - 支持动态验证时钟树配置
    - 带功耗结果估算的功耗序列
- 生成与面向Arm® Cortex®-M内核的IAR Embedded Workbench®、MDK-ARM和STM32CubeIDE（GCC编译器）兼容
- 初始化C代码
- 生成面向Arm® Cortex®-A内核（STM32微处理器）的部分Linux®设备树
- 借助STM32PackCreator开发增强型STM32Cube扩展包
- 将STM32Cube扩展包集成到项目中
- 作为可在Windows®、Linux®和macOS®（macOS®是苹果公司在美国和其他国家与地区的商标）操作系统和64位Java运行环境上运行的独立软件提供 and other countries.) operating systems and 64-bit Java Runtime environment
