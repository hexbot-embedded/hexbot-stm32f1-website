## 电子时钟

### 电子时钟简介

本次实验的主要目的是使用HexBot设备为实验平台，利用单片机内部功能和拓展的外设，设计程序开发一个电子钟系统。

所设计的电子钟系统具有以下功能：

1. 使用定时器中断实现1s的定时功能，并驱动LED灯使其闪烁；
2. 完成基本的时钟功能，通过OLED屏显示当前时间，正确走时和进位；
3. 完成万年历功能，通过 OLED屏显示是当前日期；
4. 可通过矩阵按键设置当前时间和日期；
5. 增加闹钟功能，可查看并设置闹钟时间，多个闹钟可以独立控制。

学生可在上述基本功能下，拓展诸如可以通过通信模块进行时间校准、断电后可以保存时钟时间等功能。

### 硬件设计

本次实验所使用到的HexBot硬件拓展板为:

1. OLED拓展板
2. Keyboard拓展板

其中OLED拓展板安装在HexBot主板的J2接口，键盘keyboard拓展板安装在HexBot主板的J5接口。其硬件连接如下图所示：



<img src="OLED_Clock.assets/1.png" alt="img" style="zoom: 50%;" />



在实验中，所设计的电子钟的图像界面将展示在OLED屏幕上，将选用键盘keyboard拓展板的四个开关sw1、sw2、sw3、sw4作为控制电子钟的按键，对电子钟显示内容进行切换和设置。

### 软件设计

#### CUBEMX芯片引脚分配

<img src="OLED_Clock.assets/2.png" alt="img" style="zoom:50%;" />

其中OLED屏幕使用IIC协议驱动，因此将IIC2引脚进行配置；四个开关sw1-4使用PD4、PC3、PB6、PB0四个引脚，将其配置为GPIO­_Input模式；所驱动的两排LED灯使用PC4、PC5引脚，将其配置为GPIO_Output模式。

由于需要使用单片机内部的定时器功能完成1s的定时，因此需要对时钟进行配置。这里选择开发板上的外部晶振，将芯片时钟配置为72Mhz。选择TIM1时钟通道，将其PSC设置为1999，CP设置为59999，使得产生的时钟脉冲间隔为1s。随后使能其中断。

#### 程序编程

在main函数里面开启TIM1通道的中断，并调用两个上层函数。

```c
/* USER CODE BEGIN 2 */
  ssd1306_Init();
  HAL_TIM_Base_Start_IT(&htim1);
  HAL_TIM_Base_Start_IT(&htim2);
  /* USER CODE END 2 */

  /* Infinite loop */
  /* USER CODE BEGIN WHILE */
  while (1)
  {
	  mode_check();
	  oled_show();
    /* USER CODE END WHILE */

    /* USER CODE BEGIN 3 */
  }
  /* USER CODE END 3 */
}
```

下面将简要介绍几个较为重要的函数。 

##### oled_show函数

功能：为依据状态码的不同，选择不同界面进行展示，并将OLED缓存中的数据显示在屏幕上。

```C
void oled_show(){
	//clock mode
	if(clockmode == 0){
		show_time();
	}
	//calendar mode
	else if(clockmode == 1){
		show_calendar();
	}
	//alarm mode
	else if(clockmode == 2){
		show_alarm();
	}
	//set mode
	else if(clockmode == 3 || clockmode == 4 || clockmode == 5){
		show_set();
	}
	//error mode
	else if(clockmode == 6){
		show_error();
	}
	//unnormal
	else {
		clockmode = 0;
	}

	ssd1306_Fill(Black);
	ssd1306_SetCursor(2,0);
	ssd1306_WriteString(line1, Font_11x18, White);
	ssd1306_SetCursor(2,18);
	ssd1306_WriteString(line2, Font_11x18, White);
	ssd1306_SetCursor(2,36);
	ssd1306_WriteString(line3, Font_11x18, White);
	ssd1306_UpdateScreen();
	return;
}
```









##### check_sw函数

功能：检测是否有按键被按下，以及按下的按键为哪个。

```C
//check which sw is pressed
int check_sw(){
	//check if sw1 is pressed
	if(HAL_GPIO_ReadPin(GPIOD, SW1_Pin)){
		HAL_Delay(10);
		if(HAL_GPIO_ReadPin(GPIOD, SW1_Pin)){
			return 1;
		}
	}

	//check if sw2 is pressed
	if(HAL_GPIO_ReadPin(GPIOD, SW2_Pin)){
		HAL_Delay(10);
		if(HAL_GPIO_ReadPin(GPIOD, SW2_Pin)){
			return 2;
		}
	}

	//check if sw3 is pressed
	if(HAL_GPIO_ReadPin(GPIOB, SW3_Pin)){
		HAL_Delay(10);
		if(HAL_GPIO_ReadPin(GPIOB, SW3_Pin)){
			return 3;
		}
	}

	//check if sw4 is pressed
	if(HAL_GPIO_ReadPin(GPIOB, SW4_Pin)){
		HAL_Delay(10);
		if(HAL_GPIO_ReadPin(GPIOB, SW4_Pin)){
			return 4;
		}
	}
	return 0;
}
```

<br>

### **实验现象**

实验所设计的电子钟可以完成简单计时功能。

其基本现象如下：

HexBot主板上电后，默认进入计时功能界面

按下sw4，开启时钟设置功能，轻触sw4可以切换设置位，sw3为加一，sw2为减一。结合sw2~4可对时钟时间进行修改。

<img src="OLED_Clock.assets/3.png" alt="img" style="zoom:80%;" />

按下sw1，切换至日历界面

<img src="OLED_Clock.assets/4.png" alt="img" style="zoom:80%;" />

再度按下sw1，切换到闹钟界面

<img src="OLED_Clock.assets/5.png" alt="img" style="zoom:80%;" />

