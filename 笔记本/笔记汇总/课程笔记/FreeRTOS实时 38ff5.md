# FreeRTOS实时操作系统

Property 1: April 13, 2022 10:31 PM
Property 2: FreeRTOS实时操作系统

中断

portDISABLE_INTERRUPTS关闭中断

portENABLE_INTERRUPTS打开中断

任务创建

xTaskCreate

xTaskCreateStatic

任务删除

vTaskDelete

任务挂起

vTaskSuspend

任务恢复

vTaskResume

列表插入和删除

时间片调度

taskENTER_CRITICAL

taskEXIT_CRITICAL

任务状态或信息查询

任务运行时间统计

队列操作

二值信号量

xSemaphoreGiveFromISR

xSemaphoreCreateBinary

xSemaphoreTake

计数型信号量

优先级翻转

互斥信号量操作

软件定时器

事件标志组

任务通知模拟二值信号量

任务通知模拟计数型信号量

任务通知模拟事件标志组

低功耗Tickless模式

空闲任务钩子函数

内存管理

RTOS+EMWIN