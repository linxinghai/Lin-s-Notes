# Verilog HDL
## Verilog语法

### 程序的基础结构
```Verilog
module 模块名 (端口列表);

//端口的声明（包括输入，输出，变量等）
input ...
output ...
//本模块变量，信号的声明
wire ...
reg ...
//电路功能的实际描述与时序参数
always@()
begin
	//code
end

assign ...

endmodule
```


### 模块与端口的声明

- 模块声明

	关键词
	
	模块名
	
	端口列表

- 端口类型

	input
	
	output
	
	inout

- 端口声明

	<port_type> <port_name>

### 数据(变量)类型

- 类型

	- 线网型（nets type）
		
		wire，tri
		
			wire连线类型(电路中的导线（信号线）)
		
				总线声明
		
		wor，trior
		
			多重驱动时，具有线或功能的连线型
		
		wand，triand
		
			多重驱动时，具有线与功能的连线型
		
		tri1/tri0
		
			上拉电阻/下拉电阻
		
		supply1/supply0
		
			电源（逻辑1）/地（逻辑0）
	
	- register type
	
		reg
		
			寄存器型变量
		
				触发器，寄存器
		
		integer
		
			32位带符号整型变量
		
		real
		
			64位带符号实型变量
		
		time
		
			无符号时间变量
		
		除了==reg==外为纯数学的抽象描述，  不对应任何硬件电路

- 命名

	字母a-z
	
	数字0-9
	
	下划线_

### 数值(常量)表示

- 格式

	`<size>'<base format><number>`
	
	`<位宽>'<进制><数字>`
	
	使用十进制时不能使用高阻与不定态

- 负数

- 特殊数值

- Parameter参数

### 运算

- 算符

	算术运算符
		
		操作数包含Z or X，结果为X不定值
		
		保存result结果的变量位宽超过操作数，则进位bit值自动处理
		
		保存result结果的变量位宽与操作数相同，则进位bit值丢失
		
		数据形式不一致是无法运算的
	
		+
		
		-
		
		*
		
		/
		
		%
		
		**
	
	位运算符
	
		~
		
		&
		
		|
		
		^~ or ~^
	
	位移运算符
		
		<<
		
		>>
		
		<<<
		
		>>>  
	
	缩减运算符
		
		&
		
		~&
		
		|
		
		~|  
		
		^
		
		~^ or ^~
	
	关系运算符
	
		>
		
		<
		
		>=
		
		<=
	
	等式运算符
	
		==
		
		!=
		
		===
		
		!==
	
	逻辑运算符
	
		！
		
		&&
		
		||
	
	其他运算符
	
		？：
		
		{}
		
		{{}}

- 运算优先级

### 模块例化(调用低层模块)

- 例化格式

	\<component_name\> \#\<delay\> \<instance_name\> (port_list);
	
	component_name模块名
	
		待例化的低层模块名称
	
	\#delay延时
	
		模块延时
		
		可选
	
	instance_name例化名
	
		不同于模块名，不可重复
	
	port_list接口列表
	
		列出该模块所包含的接口

- 例化模块的接口连接

	两种方法来定义接口的连接
	
	按照模块接口列表的顺序
	
	按接口名

- 接口连接的规则

## 赋值语句
- assign （输出信号）

- always

	always@（事件列表）
	
	当事件列表中的信号发生改变则引发
	begin.....end间的行为
	
- &q

	各位相与

- 过程赋值

	（1）当用always块来描述组合逻辑（combinational logic）时，应当使用阻塞赋值。
	
	（2）对于时序逻辑(sequential logic)的描述和建模，应当使用非阻塞赋值。
	
	（3）在同一个always模块中，最好不要混合使用阻塞赋值和非阻塞赋值，对同一变量
	
	既进行阻塞赋值，又进行非阻塞赋值，在综合时会出错。所以always中要么全部使用非
	
	阻塞赋值，要么把阻塞赋值和非阻塞赋值分在不同的always中书写。
	
	（4）尽量不要再在多个不同的always块中对同一变量赋值。
	
	（5）使用$strobe显示使用非阻塞赋值的变量。

	阻塞赋值

	串行赋值
	“=”
	逐个赋值
	组合逻辑时使用
	在时序电路中一般不用

	
	非阻塞赋值
	
	并行赋值
	“<=”
	同一行为下的赋值操作一次完成（由时钟信号决定）

## 门原语

	逻辑门（输出，输入......）

## 器件语句

buf
缓冲器

cmos

## 条件

q = temp?a:b;

判断

	if begin end else begin end

选择

	case  begin end default endcase

## 循环

forever

	genvar

repeat

while

for

## 结构说明

initial
textbook 的赋值语句

always

task

function

## 编译预处理

define

include

timescale
时间单位

---

## 基础

教程

简介

主要应用 专用集成电路（ASIC），就是具有专门用途和特殊功能的独立集成电路器件。 Verilog 作为硬件描述语言，主要用来生成专用集成电路。 主要通过 3 个途径来完成： 1、可编程逻辑器件 FPGA 和 CPLD 是实现这一途径的主流器件。他们直接面向用户，具有极大的灵活性和通用性，实现快捷，测试方便，开发效率高而成本较低。 2、半定制或全定制 ASIC 通俗来讲，就是利用 Verilog 来设计具有某种特殊功能的专用芯片。根据基本单元工艺的差异，又可分为门阵列 ASIC，标准单元 ASIC，全定制 ASIC。 3、混合 ASIC 主要指既具有面向用户的 FPGA 可编程逻辑功能和逻辑资源，同时也含有可方便调用和配置的硬件标准单元模块，如CPU，RAM，锁相环，乘法器等。

环境搭建

	Quartus II   Modelsim 

设计方法

设计方法

顶层模块

子模块

叶模块

设计流程

需求分析

功能划分

HDL描述

功能仿真(前仿真)

逻辑综合

布局布线

时序仿真(后仿真)

下载生产

基础语法

格式

注释

标识符与关键字

数值表示

数值类型

整数数值表示方法

指明位宽

不指明位宽

负数

实数表示方法

十进制

科学计数法

字符串表示方法

数据类型

线网wire

寄存器reg

向量

整数,实数,时间寄存器变量

整数(integer)

实数(real)

时间(time)

数组

存储器

参数

字符串

表达式

表达式

操作数

操作符

算术操作符

关系操作符

等价操作符

逻辑操作符

按位操作符

归约操作符

位移操作符

拼接操作符

编译指令

'define,'undef

'include

'timescale

'default_nettype

'resetall

'celldefine,'endcelldefine

'unconnected_drive,'nounconnected_drive

连续赋值

关键词:assign ,全加器

时延

关键词:时延,惯性时延

过程结构

initial

always

过程赋值

阻塞赋值

非阻塞赋值

并行

时序控制

时延控制

事件触发

边沿触发

电平触发

语句块

顺序块

并行块

嵌套块

命名块

disable

条件语句

关键词:if,选择器

多路分支语句

关键词:case,选择器

case

casex/casez

循环语句

关键词:while,for,repeat,forever

while

for

repeat

forever

过程连续赋值

关键词:deassign,force,release

assgin

deassgin

force

release

模块与端口

关键词:模块,端口,双向端口,PAD

模块

端口

端口列表

端口声明

模块例化

关键词:例化,generate,全加器,层次访问

命名端口连接

顺序端口连接

端口连接规则

用generate进行模块例化

层次访问

带参数例化

关键词:defparam,参数,例化,ram

defparam语句

带参数模块例化

区别与建议

函数

关键词:函数,大小端转换,数码管译码

函数

常数函数

automatic函数

数码管译码

任务

关键词:任务

任务与函数的区别

任务

状态机

关键词:状态机,售卖机

竞争与冒险

关键词:竞争,冒险,书写规范

避免Latch

关键词:触发器,锁存器

仿真激励

关键词:testbench,仿真,文件读写

流水线

关键词:流水线,乘法器

除法器设计

并行FIR滤波器设计

串行FIR滤波器设计

CIC滤波器设计

FFT设计

DDS设计

数值转换

---

## 进阶

数字逻辑设计

编码风格

门的类型

	关键词:三态门,上下拉,选择器

开关级建模

	关键词:MOS,CMOS,双向开关,PAD

门延迟

	关键词： 门延迟， D 触发器

UDP基础

延迟模型

	关键词： 分布延迟， 集总延迟， 路径延迟

specify块语句

	关键词： specify， 路径延迟

建立时间和保持时间

	关键词： 建立时间， 保持时间

时序检查

	关键词： setup hold recovery removal width period

延迟反标注

	关键词： 延迟反标注， SDF

同步与异步

	关键词： 同步，异步

跨时钟域传输

FIFO设计

	FIFO原理

		工作流程
		
		读写时刻
		
		读写状态
		
		写满状态

	FIFO设计

		设计要求
		
		双口RAM设计
		
		计数器设计
		
		FIFO调用

复位简介

	关键词： 同步复位， 异步复位

时钟简介

时钟分频

	关键词：偶数分频，奇数分频，半整数分频，小数分频

时钟切换

低功耗简介

	关键词：开关功耗，内部功耗，静态功耗

系统级低功耗设计

RTL级低功耗设计

显示任务

	关键词：$display, $write, $strobe, $monitor

文件操作

随机数及概率分布

实数整数转换

	关键词 ：定点数, 浮点数, $realtobits, $bitstoreal

其他系统任务

	仿真控制：$finish, $stop

PLI简介

TF子程序

TF子程序列表

ACC子程序

ACC子程序列表

逻辑综合

可综合性设计

---

sjljsjxmjc

逻辑代数基础

数制转换

数制

不同数制之间的转换

编码

8421BCD

2421BCD

5421BCD

余三码

循环码

奇偶校验码

ASCII

逻辑函数的描述

与

或

非

逻辑函数的化简

集成门电路

	TTL门电路的测试
	
	COMS门电路的测试

数字逻辑开发工具

组合逻辑电路

	加法器
	
	编码器
	
	译码器
	
	数值比较器
	
	数据选择器
	
	数据分配器

触发器

	RS触发器
	
	D触发器
	
	JK触发器

寄存器

	数据寄存器
	
	位移寄存器

同步计数器

	同步加法计数器
	
	同步减法计数器

异步计数器

	异步加法计数器
	
	异步减法计数器

环形计数器
	
	模4环形计数器
	
	模7扭环形计数器

数字逻辑系统综合设计
	
	跑马灯控制器
	
	电子骰子控制器
	
	二位BCD码计数器
	
	交通灯控制电路

有限状态机设计技术

	有限状态机的基本概念和传统设计技术
	
	用状态机编辑器设计状态机
	
	Moore型状态机实例---步进电机控制器设计

---

Verilog HDL    
模块例化逻辑值0电路接GND1电路接VCCX不定状态Z悬空进制2 8 10 16进制b o d h<二进制位宽>'<进制><数值>标识符 定义模块名，端口名，信号名可由字母，数字，$符号和_(下划线)符号组合区分大小写

## 关键词
```Verilog
always，产生一个函数语句输出  
and， 与元件  
assign，产生一个输出  
begin，语句开始  
buf，缓冲器  
bufif0，  
bufif1，  
case，选择  
casex，  
casez，  
cmos，coms元件  
deassign，   
default，选择中的其余项  
defparam，  
disable，  
edge，边沿  
else，否则  
end，语句结束  
endcase，选择语句结束  
endmodule，模块结束  
endfunction，函数结束  
endprimitive,   
endspecify,   
endtable，   
endtask，   
event， 事件  
for， 循环  
force，   
forever，   
fork，   
function，函数  
highz0，  
highz1,   
if，判断  
initial, 赋值  
inout, 输入输出通道  
input，输入  
integer，整数  
join,参加  
large，  
macromodule，宏模块  
medium，  
module， 模块  
nand，与非  
negedge，下降沿  
nmos，  
nor，或非  
not，非元件  
notif0，  
notifl,   
or, 或元件  
output, 输出  
parameter, 参数常量  
pmos,   
posedge, 上升沿  
primitive,   
pull0,   
pull1,   
pullup,   
pulldown,   
rcmos,   
reg, 寄存器型变量  
releses,   
repeat,   
mmos,   
rpmos,   
rtran,   
rtranif0,  
rtranif1,  
scalared,  
small，  
specify，  
specparam，  
strength，  
strong0,   
strong1,   
supply0, 逻辑值  
supply1,   
table,   
task, 要求  
time, 时间变量  
tran,   
tranif0,   
tranif1,   
tri, 三态节点  
tri0,   
tri1,  
triand,   
trior，   
trireg，  
vectored，  
wait，  
wand，  
weak0，  
weak1，  
while， 循环  
wire，节点或连接  
wor,   
xnor， 同或  
xor异或元件
```
