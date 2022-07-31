# VHDL

```VHDL
libray IEEE;
use IEEE.std_logic_1164.dll;
use IEEE.std_logic_unsigned.dll;
entity count is
  port(clock,reset: in std_logic
  dataout : out std_logic_vector(3 downto 0)
);
end count;

architecture behaviorl of count is
signal databuffer : std_logic_vector(3 downto 0);
begin
  dataout<=databuffer;

  process(clock,reset)
  begin
    if(reset='1')then  databuffer<="0000";
    elsif(clock'event and clock='1')then
    if databuffer="1000" then databuffer<="0000"; 
    else databuffer<=databuffer+'1';
    end if;
  end if;
end process;

end behaviorl;
```
## [基本结构](https://www.eefocus.com/hrbeulvcaho/blog/12-11/289109_978e2.html)

- 实体
```VHDL
Entity 实体名 is
  PORT
  (
    端口名1，端口名N：方向：类型
  ）;
  [端口说明]
End Entity;
```

generic类属说明语句
>用于改变一个设计实体或元件内部电路的结构和规模
>
>引到一个类属参量表
>表中提供时间参数及总线宽度等内部信息
>
>格式:
>generic(常数名 数据类型 := 设定值)

port端口说明
>in输入
>out输出
>buffer缓冲,内部反馈
>inout双向,也能用于内部反馈
>linkage连接

- 结构体
	```VHDL
Arcthitecture 构造体名 of 实体名 is
[定义语句] 内部信号、常数、元件、数据类型、函数等的定义
begin
  [
    并行处理语句和
    block、
    process、
    function、
    procedure
  ]
end 构造体名;
	```
	- 进程结构

	- 子程序
		
		过程
		首定义过程接口 体描述具体算法
		```VHDL
	procedure 过程名
	(
	参数名[,参数名...]:[端口模式]数据类型;
	参数名[,参数名...]:[端口模式]数据类型;
	....
	)过程首
	
	procedure 过程名
	(
	参数名[,参数名...]:[端口模式]数据类型;
	参数名[,参数名...]:[端口模式]数据类型;
	....
	) is
	
	[过程说明部分;]
	
	begin
	  <过程语句部分>;
	end [procedure] <过程名>;
		```
		- 顺序语句
		
		赋值语句
		>变量赋值 变量名 := 表达式
		>信号赋值 信号名 <= 信号变量表达式
		
		wait
		
		assert
		
		if
		
		case
		
		loop
		```VHDL
		[标号]: for 循环变量 in 离散范围 
		loop
		  顺序处理语句;
		end loop [标号];
		
		[标号]:while 循环条件 loop
		   顺序处理语句;
		end loop [标号];
		```
		并行语句
		
		函数

	- 块结构

- 配置
```VHDL
configuration 配置名 of 实体名 is
  for 选配结构体名
  end for;
end:配置名;
```

- 库
> libray<br>
>5种库
>IEEE
>STD
>ASIC
>WORK<br>
>格式:
>libray 库名;
>use 包集合名;<br>
>程序包

	包

## 语言要素

- 语法规则

	数学表示
	
	字符串型文字
	
	数位字符串
	
	标识符
	
	下标名

- 数据对象
	
	- 常量(constant)
	
	- 变量(varible)
	
	- 信号(signal)

- 数据类型

- 操作符

## 描述风格

行为描述
>仅描述行为,不描述或指明行为电路结构

数据流描述
>寄存器传输RTL

结构化描述

## 状态机

### 状态机概述组合
>Moore 输出仅与当前状态有关
>Mealy 输出与当前状态和输入信号均有关系

### 分类

实体

说明

状态转换进程

时序控制进程

辅助进程

## 其他

设计单元

对象操作符数据类型

控制语句及模块

## 模块

结构体
```VHDL
arcthitecture 结构体名 of 实体名 is
[定义语句]内部信号,常数,元件,数据类型,函数等定义
begin
  [并行处理语句和block,process,function,procedure]
enf 结构体名;
```

块
```VHDL
block
[定义语句]
begin
  [并行处理语句concurrent statement]
end block 块名
```
条件块
```VHDL
block[(布尔表达式)]
[定义语句]
begin
  [并行处理语句concurrent statement]
  [信号]<=guarded[信号,时延];
end block 块名
```
子程序
```VHDL
[进程名:]
process [(触发信号列表)]
[定义语句;]
begin
  [并行处理语句concurrent statement]
end
```
过程
```VHDL
procedure 过程名 (参数1,参数2....) is
[定义语句]
begin
  [顺序执行语句]
end 过程名
```
函数
```VHDL
function 函数名 (参数1,参数2...)
[定义语句]
return 数据类型名 is [定义语句]
begin
  [顺序执行语句]
  return [返回变量名]
end 函数名
```


## [关键词](https://max.book118.com/html/2016/0322/38320649.shtm)

```VHDL
ABS绝对值  
ACCESS  
AFTER  
ALIAS  
ALL  
AND与  
ARCHITECTURE  
ARRAY  
ASERT  
ATTRIBUTE  
BEGIN  
BLOCK块  
BUFFER缓冲  
BUS总线  
CASE选择  
COMPONENT  
CONFIGURATION  
CONSTANT  
DISCONSTANT  
DOWNTO由高向低  
ELSE否则  
ELSIF否则如果  
END结束  
ENTITY  
EXIT  
FILE  
FOR循环  
FUNCTION函数  
GENERATE  
GENERIC  
GROUP  
GUARDED  
IF判断  
IMPURE  
IN在  
INERTIAL  
INOUT输入输出  
IS是  
LABEL  
LIBRARY  
LINKAGE  
LITERAL  
LOOP循环  
MAP  
MOD  
NAND  
NEW  
NEXT  

NOR或非  
NOT非  
NULL空  
OF ...的..  
ON  
OPEN开  
OR或  
OTHERS  
OUT输出  
PACKAGE包  
PORT端口  
POSTPONED  
PROCEDURE过程  
PROCESS子程序  
PURE  
RANGE类型  
RECORD  
REGIDTER  
REJECT  
REM  
REPORT  
RETURN返回  
ROL  
ROR  
SELECT  
SEVERITY  
SIGARED  
SIGNAL信号  
SLA  
SLL  
SRA  
SUBTYPE  
THEN当   则  (一般与判断连用)  
TO由低向高  
TRANSPORT  
TYPE类型  
UNAFFECTED  
UNITS  
UNTIL  
USE使用  
VARIABLE  
WAIT等待  
WHEN  
WHILE循环  
WITH  
XNOR同或  
XOR异或

保留字

AGGRGEATE  
ALLOCATOR  
BIT位  
BIT_VECTOR  
BOOLEAN  
CHARACTER  
COMPOSITE  
CONCANTENATION  
DELAY延迟  
DRIVER  
ENUMERATION  
EVENT事件  
EXPRESSION  
IDENTIFIER  
INTEGER  
NAME名字  
OPERATORS  
PHYSICAL  
RESOLUTION  
RESUME  
SCALAR  
SLICE  
STANDARD  
STABLE  
STD_LOGIC  
STD_LOGIC_1164  
STD_LOGIC_VECTOR  
STRING  
SUSPEND  
TESTBENCH  
VECTOR  
VITAL  
WAVEFORM
```
