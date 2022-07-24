## 点亮LED

### IO口简介

  本章将要实现的是控制HEXBOT中的ST-LINK板上的两组LED实现一个交替闪烁的效果，该实验的关键在于学习如何控制HEXBOT上STM32的IO口输出。了解了IO口是如何输出的，就可以实现跑马灯。通过这一章的学习，你需要初步掌握STM32基本IO口的使用，这将是你迈向STM32的第一步。

每个IO口都可以自由编程，IO口寄存器要按 32 位字被访问。
很多IO口都是 5V 兼容的，I/O Level 标 FT 的就是 5V 电平兼容的。

##### STM32 的 IO 口可以由软件配置成如下 8 种模式：

###### 4种输入模式：

1、 输入浮空
2、 输入上拉
3、 输入下拉
4、 模拟输入

###### 4种输出模式：

5、 开漏输出
6、 推挽输出
7、 推挽式复用功能
8、 开漏复用功能

HEXBOT的编程一般采用CubeIDE软件来完成，因此在定义单片机的IO口可以在软件内置的CubeMX中来完成，而不需要像Keil中那样来手动定义IO。

STM32 的每个 IO 端口都有 7 个寄存器来控制。他们分别是：

2 个 32 位的端口配置寄存器 CRL 和 CRH；
2 个 32 位的数据寄存器 IDR 和 ODR；
1 个 32 位的置位/复位寄存器BSRR；
1个 16 位的复位寄存器 BRR；
1 个 32 位的锁存寄存器 LCKR。
CRL 和 CRH 控制着每个 IO 口的模式及输出速率。

IDR 是一个端口输入数据寄存器，只用了低 16 位。该寄存器为只读寄存器，并且只能以16 位的形式读出。

ODR 是一个端口输出数据寄存器，也只用了低 16 位。该寄存器为可读写，从该寄存器读出来的数据可以用于判断当前 IO 口的输出状态。而向该寄存器写数据，则可以控制某个 IO 口的输出电平。

BSRR 寄存器是端口位设置/清除寄存器。该寄存器和 ODR 寄存器具有类似的作用，都可以用来设置 GPIO 端口的输出位是 1 还是 0,该寄存器通过举例子可以很清楚了解它的使用方法。例如:
你要设置 GPIOA 的第 1 个端口值为 1，那么你只需要往寄存器 BSRR 的低 16 位对应位写 1 即可：GPIOA->BSRR=1<<1;你要设置 GPIOA 的第 1 个端口值为 0，你只需要往寄存器高 16 位对应为写 1 即可：GPIOA->BSRR=1<<(16+1)

BRR 寄存器是端口位清除寄存器。该寄存器的作用跟 BSRR 的高 16 位雷同。

I/O口输出模式下有三种输出速度可选（2MHz，10MHz，50MHz），这个速度是指I/O口驱动电路的响应速度；I/O管脚内部有多个响应不同的驱动电路，用户可以根据自己的需要选择合适的驱动电路。


需要注意的是：

GPIO口设置为输入时，输出驱动电路与端口是断开的，所以这时配置输出速度是无意义的；
在复位期间和刚复位后，复位功能未开启，I/O端口被配置成浮空输入模式；
所有端口都有外部中断能力，当使用外部中断功能时，端口必须设置成输入模式；
GPIO的配置具有上锁的功能，当配置好GPIO后，可以通过程序锁住配置组合，知道下次芯片复位才能解开；

### 硬件设计

 本实验所涉及到的硬件只有LED，需要用到的HEXBot板为HEXBot主板和ST-Link板，不需要接其他板块。ST-Link板需要接在主板的Port0口才可以下载程序，我们点亮LED也是控制的ST-Link板上的两组LED。

其原理图如下：

![image-20220515165456131](C:\Users\LOVE\AppData\Roaming\Typora\typora-user-images\image-20220515165456131.png)

![image-20220515165548282](C:\Users\LOVE\AppData\Roaming\Typora\typora-user-images\image-20220515165548282.png)

![image-20220515165603394](C:\Users\LOVE\AppData\Roaming\Typora\typora-user-images\image-20220515165603394.png)

主板通过Port1外接ST-Link板，其中PC6和PC7分别控制ST-Link板的两组LED。

只需要设置这两个IO口的状态就可以控制LED的亮灭状态。

### 软件设计

 HEXBot使用的STM32F1系列的单片机，在CubeIDE编程里，我们新建工程时选择STM32F103VBT6芯片。完成后进入CubeMX图形编程界面，将引脚设计为如下所示样式：

![image-20220515171225019](C:\Users\LOVE\AppData\Roaming\Typora\typora-user-images\image-20220515171225019.png)

![image-20220515171243781](C:\Users\LOVE\AppData\Roaming\Typora\typora-user-images\image-20220515171243781.png)

引脚定义完成后保存，然后进编程界面，新建USER文件夹，在里面新建LED文件夹和C,H头文件，格式应为../led/led.h和../led/led.c。我们在这里编写LED的驱动程序

然后在c文件中编写以下程序

![image-20220515172024011](C:\Users\LOVE\AppData\Roaming\Typora\typora-user-images\image-20220515172024011.png)

在h文件中编写以下程序

![image-20220515172046922](C:\Users\LOVE\AppData\Roaming\Typora\typora-user-images\image-20220515172046922.png)

此时驱动程序已经编写完毕，现在我们进入主程序，打开Core/Src/main.c,这是主程序所在位置。

首先，我们需要在主程序里面添加led驱动程序的头文件，如下所示

![image-20220515172442622](C:\Users\LOVE\AppData\Roaming\Typora\typora-user-images\image-20220515172442622.png)

然后我们可以在while函数里面编写跑马灯程序：

![image-20220515172528050](C:\Users\LOVE\AppData\Roaming\Typora\typora-user-images\image-20220515172528050.png)

值得注意的是，CubeIDE软件内置的HAL库里有延时函数，因此我们不需要额外的编写延时函数，直接调用即可。

代码编写无误后，将ST-Link和电源插入电脑后，点击运行即可下载程序。程序下载完成后，ST-Link板上应该可以看到两组LED交替闪烁。

以下是软件设计里面各个函数的作用：

HAL_GPIO_WritePin   :给某个IO口写入0或者1

GPIOC:端口组号

LED1_Pin：端口标注名称

GPIO_Pin_SET:电平置位（高电平）

GPIO_Pin_RESET:电平置位（低电平）

