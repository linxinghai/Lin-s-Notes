# FPGA
>基于查找表的CLB阵列

分类

指令集

## 硬件设计语言

- 术语与概述
	- 自顶向下设计

		- 设计开发
	
			顶层模块设计
			
			底层模块设计
		
		- 设计验证
		
			模块验证
			
			综合验证
	
	- 硬件描述语言
	
	- 行为级建模
	>侧重于对模块输入/输出行为功能的描述
	
		描述电路的功能而非结构
	
		综合工具来生成正确的逻辑结构

	- 结构级建模
	>侧重于对模块内部实现的具体底层结构的描述
	>（直接描述其底层的电路结构）
	
		更侧重从具体的结构来描述电路的功能
		
		调用特定的硬件结构来实现
	
	- 其他
	
		Register Transfer Level(RTL)
		
			寄存器传输级，一种可综合的行为级描述
		
		Synthesis
		
			综合，将HDL硬件描述语言转换并优化为实际的电路
		
		RTL Synthesis
		
			寄存器传输级综合，将RTL级描述的硬件模型综合并优化为实际的门级电路
		
		RTL Simulation
		
			寄存器传输级仿真,对综合的电路测试其输出与时序
	
	- 核心分配
	
		软核
		
		固核
		
		硬核

[VHDL](笔记本/已归档/芯片设计/FPGA/VHDL.md)

[Verilog HDL](笔记本/已归档/芯片设计/FPGA/Verilog%20HDL.md)

[System Verilog](笔记本/已归档/芯片设计/FPGA/System%20Verilog.md)

[Chisel](笔记本/已归档/芯片设计/FPGA/Chisel.md)

[Scala](笔记本/已归档/芯片设计/FPGA/Scala.md)

## FPGA烧写JIC
>sof文件生成jic文件

files→convert programming files

Program file type选择JTAG indirect configuration file（.jic）

Configuration device选择需要的eeprom例如型号：EPCQ256

单击input files to convert窗口中的flashloader，右侧的add device按钮变为有效， 点击add device，选择所需型号：ArriaV 5AGXFB3H6ES

点击add sof data，然后点击input files to convert窗口中出现的sof data，右侧按钮随之变化，点击add file，选择相应的sof文件

点击generate完成文件转换

烧录JIC文件，点击菜单栏中的Program

点击左侧的Add Files，弹出对话框，选择刚才生成的output_file.jic

点击左侧的Start即可完成烧写

## 硬件项目

逻辑门

数据选择器

编/译码器

分频器

计数器

伪随机数发生器

秒计数器

相邻点累加

三角波发生器

串口数据收发

串口指令处理器

流水灯

交通灯

- 芯片
sn74hc157

- 加法器
半加器
全加器

简易可编程单元

数字滤波器

串行FIR滤波器

并行FIR滤波器

CIC滤波器

滤波算法

神经网络

信号发生器
DDS

运动目标检测

FIFO

数字电压表

高速采集处理系统

锁相环
PD
LF
VCO

深度学习神经网络加速

乘法器

除法器

FFT


设计思路

乱序执行

分支预测

近似计算

重构

改善既有代码的设计

路径

编程

语言

流程

语法

设计

验证

[书](https://hdlbits.01xz.net/wiki/Main_Page)

数字系统设计

高级数字设计

硬件设计及建模

验证与测试平台编写指南

深入浅出玩转fpga

勇敢的芯伴你玩转altera fpga

基础

电路

数电

数字集成电路

计算机体系结构与接口

数字信号处理

流程

RTl设计

仿真验证

逻辑综合

布局布线

时序收敛

硬件测试

开发工具

vivado

quartus

- 调用ip
    
    pll
    fifo
    存储器
    
    nios
    以太网控制器
    PCIe
    DDR控制器
    

时序分析

实验

数码管

流水灯

按键

红绿灯

总线通信
[由基础的效应管实现可编程芯片](笔记本/已归档/芯片设计/由基础的效应管实现可编程芯片.md)
数据与信号处理
模拟IC
射频IC
数字信号处理
[详解FPGA如何实现 cd38d](笔记本/已归档/芯片设计/FPGA/详解FPGA如何实现%20cd38d.md)
[RSIC-V](笔记本/已归档/技术/其他笔记/RSIC-V.md)