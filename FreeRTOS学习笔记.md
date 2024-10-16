> 优先级默认上限  configMAX_PRIORITIES - 1
> 任务优先级：每个任务均被分配了从 0 到 ( configMAX_PRIORITIES - 1 ) 的优先级，其中 configMAX_PRIORITIES 定义为 FreeRTOSCo nfig.h。
> 优先级数字小表示任务优先级低。[空闲任务](https://www.freertos.org/Documentation/02-Kernel/02-Kernel-features/01-Tasks-and-co-routines/15-Idle-task)的优先级为零 (tskIDLE_PRIORITY)。

> 注意：空闲任务负责释放由 RTOS 内核分配给已删除任务的 内存。因此，如果应用程序调用了 **vTaskDelete**()，请务必确保空闲任务获得足够的微控制器处理时间。任务代码分配的内存不会自动释放， 应在任务删除之前手动释放。

STM32CubeMX 生成的 FreeRTOS 的模板竟然没有 xTaskDelayUnitl 这个函数，即使我添加了它响应的宏定义，这让我感到不可思议。

我尝试移植的 FreeRTOS 任务成功了。

**任务的实现过程：** 
定义任务[[栈]] ：需要动态或者静态分配一段内存空间
![[2024-10-16 090020笔记.png]]