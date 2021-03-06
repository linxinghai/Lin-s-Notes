# IC设计

[FPGA](笔记本/已归档/芯片设计/FPGA.md)

[CPU from zero](https://www.coursera.org/lecture/jisuanji-zucheng/506-kong-zhi-xin-hao-de-ji-cheng-kRJer)

- 单片机
    
    8051
    
    STM
    
    ESP
    

Thumb‐2

- [ARM](https://www.cnblogs.com/senior-engineer/p/8668723.html)
    
    cortex
    
    flash
    
    sram
    
    fsmc
    
    apb桥
    
    ahb
    
    rcc
    
    SDIO
    
---
x86

risc_v

[基于FPGA的轻量级RISCV SoC - 云+社区 - 腾讯云 (tencent.com)](https://cloud.tencent.com/developer/article/1766398)

[基于FPGA与RISC-V的嵌入式系统设计 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/161913449)

架构

加法器的其他设计

CSA

CLA

LING

PPA

VLSI

---

IC

CPU from zero

基础构建

常开继电器

常闭继电器

继电器级

晶体管级

逻辑门电路

与非NAND

4T

与AND

子主题

非NOT

4T

或非NOR

或OR

2INV  1NAND

异或XOR

1OR 1NAND  1AND

同或XNOR

算法电路

半加器halfadd

1AND 1XOR

全加器add

2ADD 1OR

多位加法器

N(16) ADD

自增inc

1ADD16 1INV

减法sub

1INV16 1INC16  1ADD16

判0 is zero

3or  1inv

小于0 is neg

分配

管道电路

选择器(select)

1inv  2and  1or

开关(switch)

1inv  2and

记忆电路

锁存器(latch)

1inv  1or  1xor  2nand

触发器(dff)

1inv  2and  1or  2latch

寄存器(reg)

2dff

计数器(counter)

1select16  1nand  1inc16  1reg

RAM

1switch  2reg  1select16

算术逻辑单元

一元ALU(unary alu)

2inv16  3select16

ALU

2unary alu  2add16  2select16  1inv16

操作码(opcodes)

条件(conditiom)

1is zero  1is neg  2inv  4and  2or

处理器

存储器(combind memory)

2reg  1ram

译码器(instruction decoder)

分配  13and  1inv  2select16

控制器(control unit)

1instruction  2select16  1alu  1memory

PC(computer)

1clock  1rom  1control  1counter

输入输出(input and output)

1and

1select

编程

机器语言

汇编

C语言

---

单片机

8051

核

时钟

分频

PLL

滤波

cpu

存储器

SFR

PC

ACC

DPTR

SP

SBUF

子主题

rom

并行io

2mos  1not  2buf  1reg  1select  1and

串行io

TX

RX

Sbuf

中断系统

TCON

https://blog.csdn.net/Qingzhusshuiyun/article/details/78202385?utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromBaidu%7Edefault-7.no_search_link&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromBaidu%7Edefault-7.no_search_link

SCON

IE

EX0

ET0

EX1

ET1

ES

EA

IP

PX0

PT0

PX1

PT1

PS

中断向量寻址ROM

定时计数

TH TL

TCON

TMOD

双数据指针

额外的定时器

串口

max810专用复位电路

e2prom

flash

看门狗

sram

闪存

isp监控

A/D

端口

pin

30/rx

31/tx

32/it0

33/it1

34/t0

35/t1

wr/36

rd/37

vcc

rst/vpd

xtal

ea/vpp

ale/prog

psen

gnd

执行过程

stc

ram

ram地址寄存器

ram256字节

128sfrs

aux-ram1024字节

数据存储器

寄存器

ACC

B寄存器

PSW

PSW

TH/TL2

RCAP2H/L

T2CON

IP

Pinx

IE

SBUF

SCON

TH/TL1

TH/TL0

TMOD

TCON

DPH/L

双数据指针

SP

堆栈指针SP

PCON

tmp1

E2PROM  5k

程序存储器flash  8K

isp/iap

地址生成器

程序计数器

WDT

看门狗

外部中断x4

复位

ALU

control unit

定时器x3

接口

串口x1

协议接口

以太网接口

USB

并口

锁存器

驱动器

---

risc_v

子主题

Local APIC

I/O APIC

I/O 高级中断控制器

位多路复用器

毛刺容忍

支持反馈逻辑

reg

SRAM

三级缓存

DRAM

local disk

distrbuted file systems，web server

架构

special logic

turbo decoder

vertebi decoder

jd

en/decryption

network interface

lan

atm

e1/t1

lvds

stm

子主题

siwtch bus

dsp bus extension

peripheral interface

1394

usb

pci-X

hpi

configurable MMU

clock

power management

resct

test

co-processor

inter processor

mpu

configurable logic(pga)

dma

protocol processor

algorithms distributor

internal ram

dsp

---

CodingM

电与二进制

二进制与布尔代数

晶体管与逻辑门

ALU

算术

加法器

半加法器

全加法器

减法器

原码

反码

补码

乘法器

除法器

逻辑

判0

溢出

负值

奇偶

进位

CPU

寄存器

RS锁存

触发器

SRAM

断电失效

DRAM

延时失效

ROM

寻址器

数据选择器

解码电路

CPU结构

冯诺依曼结构

内存

CPU

数据寄存器x4

A,B,C,D

CU

解码器

指令寄存器x2

IC,IP

ALU

x86

ARM

SoC

汇编语言

指令

指令集

指令集架构

取指

解码

执行

计算机构成

引脚

主板

CPU

IC

GPU

CHIPSHT

USB

计算机的启动

上电

电源IC

时钟

开机

CPU

ROM

BIOS

UEFI

CHIPSHT

硬盘

SRAM

x86汇编

硬盘MBR分区中的x86汇编

硬盘结构

电机

磁头

磁盘

磁道

柱面

扇区

如何操作显卡让显示器打印字符

mov指令

通用寄存器

AX

BX

CX

SI

DI

BP

SP

地址分配

DRAM

640kb

图形

128kb

BIOS

256kb

中断向量表

boot

VGA彩色图形

64kb

黑白文本

32kb

彩色文本

32kb

栈

认识汇编以及mov指令

逻辑电路

机器语言

汇编语言

高级语言

mov 目的，源

操作单元

通用寄存器

内存单元

立即数

段寄存器

深入mov指令及内存分段了解汇编地址

mov 位宽 操作数，源

byte

word

dword

qword

内存分段

寻址空间

段寄存器

ds

偏移地址

子主题

调试汇编程序

Git代码

cd

config

add

status

汇编的加减法和循环

$ = 当前汇编地址

jmp $

等待

指令

add

sub

操作数

reg

寄存器

mem

内存

imm

立即数

标志寄存器

子主题

汇编的乘除法及栈的定义使用

打印字符串

使用汇编读取硬盘

运行启动扇区外的程序

显卡

中断向量表

x86CPU以及保护模式

32位CPU及toyOS系统设计

计算机存储体系，块设备访问及硬盘分区

FAT32文件系统

读取FAT32文件系统

程序测试的方法论

CPU的5种操作模式以及切换方法

从实模式到保护模式的切换代码

从需求到流程图再到代码

内存分页
