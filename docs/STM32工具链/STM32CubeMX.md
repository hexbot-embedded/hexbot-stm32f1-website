一、STM32CubeMX 简介
 1、STM32CubeMX 是 ST 意法半导体近几年来大力推荐的STM32 芯片图形化配置工具，目的就是为了方便开发者， 允许用户使用图形化向导生成C 初始化代码，可以大大减轻开发工作，时间和费用，提高开发效率。STM32CubeMX几乎覆盖了STM32 全系列芯片。 

在CubeMX上，通过傻瓜化的操作便能实现相关配置，最终能够生成C语言代码，支持多种工具链，比如MDK、IAR For ARM、TrueStudio等  省去了我们配置各种外设的时间，大大的节省了时间



安装CubeMx一共需要三个

 JRE （Java Runtime Environment）  Java运行环境 运行JAVA程序所必须的环境的集合
 STM32CubeMX
HAL库   STM32 HAL固件库   ST官方推出的另一套库
1安装JRE
由于 STM32CubeMX 软件是基于 JAVA 环境运行的，所以需要安装 JRE （Java Runtime Environment）才能使用，   记得选择64位的安装

官网：  https://www.java.com/en/download/manual.jsp

BD云： https://pan.baidu.com/s/1rI_XrM2SAw-6Jbvj75SWpg?pwd=hwk7 提取: hwk7 

新lian接：

BD云： https://pan.baidu.com/s/1rj56i9HS4UAaE9yEaiIsaA?pwd=ack6 提取: ack6 

1点击安装



2 修改路径 点下一步



3 等待安装完成，关闭界面



2安装STM32CubeMX
 官网：www.st.com/stm32cubemx

BD云： https://pan.baidu.com/s/1Zs_FVscmGGx6zSzcZ0L2BA?pwd=tkiv 提取: tkiv 

 STM32CubeMX(V6.1.1)

BD云： https://pan.baidu.com/s/1yKgxQk2vxyqAy4CrGHZYzA?pwd=8m4m 提取: 8m4m

2022.3.18更新 STM32CubeMX(V6.4.0)

同时CSDN下载地址：（ 我设置的是0积分加免费下载）

STM32CubeMx6.1.1版本+JRE安装包-嵌入式文档类资源-CSDN下载

 STM32CubeMx6.4.0版本+JRE安装包-嵌入式文档类资源-CSDN文库

官网下载：



在官网下载需要注册下ST官网账号,目前最新为5.3.0版本，不想在官网下可以在百度云盘下载，

1打开安装包 



2同意协议，下一步



3 勾选第一个即可，第二个选项是是否同意ST公司收集你的个人使用信息等。



4 点YES  这句话是安装本软件可能会与文件夹之前文件冲突，导致文件夹之前文件丢失 是否继续 

点继续即可



5 直接点NEXT，其他不用设置 之后开始安装



6 安装完成，点Done退出



3安装HAL库
什么是HAL固件库？

STM32 HAL固件库是Hardware Abstraction Layer的缩写，中文名称是：硬件抽象层。HAL库是ST公司为STM32的MCU最新推出的抽象层嵌入式软件，为更方便的实现跨STM32产品的最大可移植性。HAL库的推出，可以说ST也慢慢的抛弃了原来的标准固件库，这也使得很多老用户不满。但是HAL库推出的同时，也加入了很多第三方的中间件，有RTOS，USB，TCP / IP和图形等等。

和标准库对比起来，STM32的HAL库更加的抽象，ST最终的目的是要实现在STM32系列MCU之间无缝移植，甚至在其他MCU也能实现快速移植。

并且从16年开始，ST公司就逐渐停止了对标准固件库的更新，转而倾向于HAL固件库和 Low-layer底层库的更新，停止标准库更新，也就表示了以后使用STM32CubeMX配置HAL/LL库是主流配置环境；

HAL库，有在线安装、离线安装两种方式。

在线安装
打开安装好的 STM32CubeMX 软件  点上面的Help -> Manage embedded software packages 



会跳出来一个选择型号界面   勾选上你要安装的HAL库， 点击“Install Now” 直到安装成功。 如下图：



离线安装
离线安装需要下载安装包，这里提供百度云和ST官方下载方式           PS：建议在线安装  速度快，又稳定

官网：www.st.com/stm32cubemx

软件下载旁边一栏就是HAL库下载  下载对应芯片的安装包





百度云：https://pan.baidu.com/s/1dm83PbIsq7Vk9bAyFNinag 提取码: wjmd    

1直接导入安装包   Help -> Manage embedded software packages ->From Local  选择离线包即可



2直接解压

Help->Updater Settings...     可以选择HAL库安装包路径 ，默认在C盘 可以自行修改



解压到相对应路径即可



到此，恭喜你的STM32 CubeMx安装成功了。
————————————————
版权声明：本文为CSDN博主「Z小旋」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/as480133937/article/details/98885316
