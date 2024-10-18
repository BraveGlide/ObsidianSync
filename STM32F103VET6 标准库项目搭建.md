# 准备
首先，我们要知道，软件代码移植的成本是 0，所以，我们尽量不要重复造轮子，写过的代码尽量保存，这里教程提到的项目搭建也要保存好，后面会经常使用的。

首先我们需要准备一些项目搭建的库文件和开发环境
1. [STM32固件库下载](https://www.st.com.cn/zh/embedded-software/stsw-stm32054.html)
2. [STM32芯片包下载](https://www.keil.arm.com/packs/stm32f1xx_dfp-keil/boards/)
3. [Keil5下载](https://www.keil.com/download/product/)(这里下载MDK-ARM，因为STM32是ARM架构)
# 开始
首先，先安装 Keil5，安装过程不多讲。

然后安装 STM32 芯片包，安装方法就是双击 STM32 的芯片包，然后就根据提示操作即可。

所有软件安装完成后我们就开始移植了，别眨眼，跟着操作，一步一步来。
1. 创建 Keil 项目
