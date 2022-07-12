# FPGA
基于查找表的CLB阵列

分类

指令集

## 硬件设计语言

[[VHDL]]

[[Verilog HDL]]

[System Verilog](System%20Ver%201019a.md)

[Chisel](Chisel%2040d40.md)

[Scala](Scala%20ae748.md)

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

芯片
sn74hc157

加法器
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
[[由基础的效应管实现可 ef57c]]
数据与信号处理
模拟IC
射频IC
数字信号处理
[[详解FPGA如何实现 cd38d]]
[[risc-v]]