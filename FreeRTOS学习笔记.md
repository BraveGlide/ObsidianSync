> 优先级默认上限  configMAX_PRIORITIES - 1
> 任务优先级：每个任务均被分配了从 0 到 ( configMAX_PRIORITIES - 1 ) 的优先级，其中 configMAX_PRIORITIES 定义为 FreeRTOSCo nfig.h。
> 优先级数字小表示任务优先级低。[空闲任务](https://www.freertos.org/Documentation/02-Kernel/02-Kernel-features/01-Tasks-and-co-routines/15-Idle-task)的优先级为零 (tskIDLE_PRIORITY)。

> 注意：空闲任务负责释放由 RTOS 内核分配给已删除任务的 内存。因此，如果应用程序调用了 **vTaskDelete**()，请务必确保空闲任务获得足够的微控制器处理时间。任务代码分配的内存不会自动释放， 应在任务删除之前手动释放。

STM32 的系统时钟频率修改
**STM32F407ZGT6**：在`system_stm32f4xx.c`里面修改，这个文件里定义了`PLL_M`、`PLL_N`、`PLL_P`
`SYSCLK`的频率等于$SYSCLK=(f_{PLL}*PLL_N)/(PLL_M*PLL_P)$

# 查看系统时钟主频
```c
RCC_ClocksTypeDef RCC_Info;
RCC_GetClocksFreq(&RCC_Info);
freq=RCC_Info.SYSCLK_Frequency;
```