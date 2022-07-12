# STM32
## 构成
### 时钟树

	时钟源
		
		HSI（高速内部时钟）8MHz RC晶振
		
		HSE（高速外部时钟）4-16MHz
		
		LSI（低速内部时钟）40kHZ RC晶振
		
			为独立看门狗提供时钟  也可以作为RTC的时钟源
		
		LSE（低速外部时钟）32.768kHz
		
			主要是RTC的时钟源
		
		PLL(锁相环倍频输出)   2-16倍  最大不超过72 MHz
		
			由高速时钟提供输入，输出放大后的时钟

时钟输出

时钟总线

	MCO（主时钟输出）
	
	OSC（输入与输出外部高速时钟信号）
	
	OSC32（输入与输出外部低速时钟信号）

RTC（复位时钟）

CSS时钟安全系统(当HSE时钟故障时由CSS触发中断（CSSI）并输入TIM1)

看门狗时钟

RCC寄存器

	RCC_CR
	
	RCC_CFGR
	
	RCC_CIR
	
	RCC_APB2RSTTR
	
	RCC_APB1RSTR
	
	RCC_AHBENR
	
	RCC_APB2ENR
	
	RCC_APB1ENR
	
	RCC_BDCR
	
	RCC_CSR

USBCLK

SYSCLK

	AHB分频

		APB
			
			APB1
			
				电源接口
				
				备份接口
				
				CAN
				
				USB
				
				I2C
					
					I2C1
					
					I2C2
			
				UART
				
					UART2
					
					UART3
				
			APB2
				
				UART1
				
				SPI1
				
				Timer1
				
				ADC
				
					ADC1
					
					ADC2
					
					IO口

	外部时钟使能
	

![框图](Pasted%20image%2020220629140133.png)*时钟树*

函数
```C
static void SetSysClock（void）
{
 #ifdef SYSCLK_FREQ_HSE
 SetSysClockToHSE():
}
```

### 寄存器

固件库函数

	将寄存器的地址与调用函数进行包装

结构体

	NVIC
	
	GPIO
	
	USART
	
	RCC
	
	TIM
	
	ADC

### 通用与复用功能I/O

GPIO(输入输出通用管脚)
	
	组成
	
		配置寄存器
		
			CRL
			
			CRH
	
		数据寄存器
		
			IDR
			
			ODR
	
		位置位/复位寄存器
		
			BSRR
		
		复位寄存器
		
			BRR
		
		锁存寄存器
		
			LCKR

	初始化函数
	
		时钟使能-RCC_APB2PeriphClockCmd
		
		端口配置-GPIO_InitTypeDef-端口成员
		
		初始化参数-GPIO_INIT
		
		电平设置
		
			GPIO_setbits
			
			GPIO_Resetbits
	
AFIO(复用与重映射)

### PWM

AFIO_MAPR

	一般步骤
	
		开启时钟以及复用功能时钟，配置GPIO为复用输出
		
		设置复用功能重映射到GPIO上
		
		初始化时钟，设置时钟的预载值与预分频
		
		设置时钟通道的PWM模式，使能时钟的通道输出
		
		使能时钟
		
		修改TIMX_CCRx来控制占空比

### 中断/事件

	事件是中断的触发源
	
	控制器
	
		嵌套向量中断控制器
		
		外部中断/事件控制器
	
	中断类型
	
		外部中断
		
			使能AFIO时钟
			
			EXTI中断线配置
			
			端口初始化
			
			NVIC中断控制器配置
			
				NVIC
				
				结构体成员
			
			中断服务函数
		
		串口中断
		
			子主题
		
		定时器中断
	
	中断配置
	
		时钟使能
		
		中断控制器分组的优先级设置
		
		外部中断初始化
		
		NIVIC中断分组设置中断优先级
	
	定时器（1ms）
	
		分类
		
			高级定时器（Tim1，Tim8）
			
			通用定时器
			
				时钟总线使能(RCC)
				
				初始化(TIM_TimeBaesInit)
				
					计算公式：Tout= ((arr+1)*(psc+1))/Tclk；
				
					1ms定时：(999+1)*(7199+1)/7200
				
					长时间中断需要用同个时钟重复计时拼接而成
				
				DIER允许更新中断（TIM_ITConfig）
				
				中断控制器设置（NVIC）
				
					优先级设置
					
					开通道
				
				时钟使能（TIM_Cmd）
				
				中断服务（IRQHandler）
				
					中断检测
					
					中断服务项
					
					关闭中断
			
			基本定时器（Tim6，Tim7）
		
		初始化
		
			设置下次更新后自动重载的值
			
			时钟频率的除数的预分频
			
			模式设定
			
			指定参数的初始化时间基数单位

### 串口（USART）

	一般步骤
	
		串口时钟使能，GPIO时钟使能
		
		串口复位
		
		GPIO端口模式设置
		
		串口参数初始化
		
		开启中断并且初始化NVIC（如果需要开启中断才需要这步骤）
		
		使能串口
	
		编写中断处理函数
		
			是否触发接收中断
			
			接收是否已完成
		
				已完成
				
				是否接收到结束位0x0d
			
					判断校验位是否正确
			
						数据错误重新开始
			
						完成接收
			
					判断结束位
			
						将数据存入数组
				
							数据是否越界
			
			其他中断操作
	
	串口寄存器
	
		USART_DR
		
		USAART_SR
	
	关于数据的收发
	
		数据寄存器USART_DR
		
		实现函数
		
			USART_SendData
			
			USART_ReceiveData
		
		案例实验
		
			发送
			
			复读
	
	串口状态USART_SR
	
		RXNE
		
		TC
		
		实现函数
	
			USART_GetFlagStatus
	
	初始化
	
		串口时钟使能
		
		TX与RX管脚初始化
		
			GPIO
		
		中断配置
		
			NVIC
		
		USART寄存器配置
		
			USART
		
			结构体成员
		
				USART_BaudRate
				
				USART_WordLength
				
				USART_StopBits
				
				USART_Parity
				
				USART_HarwareControl
				
				USART_Mode
		
		开启接收中断
		
			USART_ITConfig
		
		使能串口
		
			USART_Cmd
	
	得到数据长度需要与&上0x3f
	
	中断服务
	
		获得中断状态
	
			USART_GetITStatus

### flash memory（快闪存储器）
	
	模块组织
	
		主存储器
	
		信息块
	
			启动程序代码
			
			用户选择字节
	
		闪存存储器接口寄存器
		
			FLASH_ACR
			
			FPEC键寄存器FLASH_KEYR
			
			闪存状态寄存器FLASH_SR
			
			闪存控制寄存器FLASH_CR
			
			闪存地址寄存器FLASH_AR
			
			选择字节寄存器FLASH_OBR
			
					写保护寄存器FLASH_WRPR
	
	一般步骤
	
		读FLASH_CR的LOCK位
		
		LOCK位 = 0
		
		置FLASH_CR的PG位 = 1
		
		在指定的地址写入半字（16位）
		
		FLASH_SR的BSY位 = 1
		
		擦除需要修改地址的内容
		
		该编程地址并检查写入的数据
	
	内存
		
		内存读取
		
			data = *(vu 8*)addr
	
		内存的编程和擦除
		
			锁定解锁函数
		
				void FLASH_Lock(void)；
				
				void FLASH_Unlock(void)；
		
			写操作函数
			
				FLASH_ProgramWord(uint32_t Address, uint32_t Data);  
				FLASH_ProgramHalfWord(uint32_t Address, uint16_t Data);  
				FLASH_ProgramOptionByteData(uint32_t Address, uint8_t Data);
		
			擦除函数
			
				FLASH_ErasePage(uint32_t Page_Address);  
				FLASH_EraseAllPages(void);  
				FLASH_EraseOptionBytes(void);
		
			获得FLASH状态
			
				FLASH_GetStatus
				
			等待操作完成函数
			
				FLASH_WaitForLastOperation
			
			读FLASH特定地址数据函数
			
				STMFLASH_ReadHalfWord
	
	注意事项
	
		32复位后FPEC模块是被保护的，不能写入FLASH_CR寄存器，  通过写入特定的序列到FLASH_KEYR寄存器可以打开FPEC模块只有在写保护被解除后，  我们才能操作相关寄存器，叫UnLock
	
			键值不正确会产生总线错误
	
		每次必须写入16位

### 环境

### 案例实验

	标准
		
		已完成
			
			跑马灯()
			
			蜂鸣器()
			
			按键输入()
			
			串口()
			
			定时器()
			
			PWM()
			
			flash()

			看门狗()
			
			OLED 屏幕()
			
			TFTLCD显示()
			
			ADC()

		未完成
			
			485()
			
			外部中断
			
			输入捕获  ()

			USMART调试组件
			
			RTC实时时钟
			
			温度传感
			
			摄像头
			
			2.4G通信

	自定义
	
		双芯片通信
		
		有线（已经完成）
		
		无线
## 项目
[[水质监测设备 57254]]
[[万年历 7f6db]]
[[奶茶机 d444f]]
[[农业灌溉设备 8752c]]
[[平衡车 631fa]]
[[充电桩 c677a]]
[[高压配电测试设备 6c5f9]]
[[光立方 98a92]]
[[广州塔 19f3f]]
[[红外驱鼠器 360de]]
[[智慧管廊]]