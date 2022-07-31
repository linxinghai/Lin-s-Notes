# C
#runoob
#MyCode 
```C
1.
#include 头文件引用    ■stdio.h初始库    ■stdlib.h  
    int atoi(const char *nptr);(字符串转整型)  
    itoa  
    sprintf整型装字符串    (类型说明符*）malloc(size)申请内存    (类型说明符*）calloc(items，size)  
    free(p)释放内存    ■stdrag.h  
    k=x+rand（）%(y-x+1)*k  
    srand（(unsigned int）time(null）） system（） exit（）    ■math.h   
    pow指数 sqrt根式 abs绝对值 mod取整(求余)  
    exp以e为底的指数 ciel返回大于或者等于指定表达式的最小整数    ■reg51.h  
    intrins  
        _crol_ _cror_ _nop_(左移，右移，空但占用机器时长)    ■complex  
    real()、imag()、norml()、conjl()、expl()、logl()、log10l()、powl()、sqrtl()、sinl()、sinhl()    ■time.h  
    sleep（）    ■windows.h  
    HWND    ■string.h  
    strcopy    ■iorstream  
pthread    ■thread  
      
  
  
2.
#define 宏定义  
  
类型:int float double char long short void null  
  
格式:%d整型 %c字符 %f实型 %p地址 %s字符串(修饰词 long short）  
  
类型转换(int)a  
main return  
  
输入输出:  
格式化sanf printf  
字符getchar putchar (前缀s为字符串型，前缀f为文件流）gets puts fgetc fputc  
  
循环判断:for if else  
do switch while break continue  case default  
作用域:extern intern none（文件，块，函数auto ：声明自动变量（一般省略）static ：声明静态变量  
int ： 声明整型变量或函数long ：声明长整型变量或函数返回值类型  
float ：声明浮点型变量或函数返回值类型double ：声明双精度浮点型变量或函数返回值类型char ：声明字符型变量或函数返回值类型short ：声明短整型变量或函数  
signed ：声明有符号类型变量或函数  
unsigned ：声明无符号类型变量或函数const ：声明只读变量  
register ：声明寄存器变量  
  
struct ：声明结构体类型常与typedef连用定义一种新的数据类型enum ：声明枚举类型  
union：声明共用体类型  
  
switch :用于开关语句  
case ：开关语句分支  
default ：开关语句中的“默认”分支  
  
break ：跳出当前循环  
continue ：结束当前循环，开始下一轮循环do ：循环语句的循环体  
for ：一种循环语句while ：循环语句的循环条件  
  
if :条件语句 else ：条件语句否定分支（与 if 连用）  
  
extern ：声明变量或函数是在其它文件或本文件的其他位置定义  
  
goto ：无条件跳转语句（跳转到对应标签）return ：子程序返回语句（可以带参数，也可不带参数）  
  
sizeof ：计算数据类型或变量长度（即所占字节数）  
  
typedef ：用以给数据类型取别名
void ：声明函数无返回值或无参数，声明无类型指针  
volatile ：说明变量在程序执行中可被隐含地改变  
  
算符  
!  
++ -- + -  
* / %  
<  <= > >=  
== !=  
&&  
||  
？：  
= += -= *= /= %=  
，  
  
转义含义  
\a声音警铃  
\b退格  
\f表单  
\n换行  
\r回车  
\t水平制表  
\v垂直制表  
[\\反斜线](file://反斜线)  
\"双引号  
\'单引号  
\？问号  
  
指令  
  
inline  
restrict  
_Bool  
_Complex  
_Imaginary  
  
  
_Alignas  
_Alignof  
_Atomic  
_Static_assert  
_Noreturn  
_Thread_local  
_Generic  
  
局部变量归栈，动态内存归堆  
  
[http://www.gnu.org/software/libc/manual/html_node/index.html](http://www.gnu.org/software/libc/manual/html_node/index.html)

typedef {

当前状态码

函数指针

}
```


## 教程
基础
关键词、常量、变量
数据类型
输入、输出、格式化
运算符
表达式
语句
判断
循环
数组
结构体、共用体、枚举、位操作
函数
指针
内存管理

## 
System()

参数为cmd指令

[C/C++学习----使用C语言代替cmd命令、cmd命令大全 - 千古壹号 - 博客园 (cnblogs.com)](https://www.cnblogs.com/qianguyihao/p/4148458.html)
[c语言操作excel](https://blog.csdn.net/hongzhen91/article/details/57422897?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522163581367316780261914230%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=163581367316780261914230&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-57422897.pc_search_result_control_group&utm_term=C%E8%AF%AD%E8%A8%80%E5%A6%82%E4%BD%95%E6%93%8D%E4%BD%9Cexcel%E6%96%87%E4%BB%B6&spm=1018.2226.3001.4187)

## 菜鸟教程
C

cn

基础

简介

环境配置

文本编辑器

C编译器

Unix/Linux

Mac OS

Windows

MinGW

程序结构

实例

预处理器指令

函数

变量

语句&表达式

注释

编译&执行

gcc xxxx.c

gcc test1.c test2.c -o main

基本语法

C的令牌

分号

注释

标识符

关键词

volatile

register

C中的空格

数据结构

基本类型

整数类型

char

unsigned char

signed char

int

unsigned int

short

unsigned short

long

unsigned long

1字节

2字节

4字节

浮点类型

float

double

long double

4字节

8字节

16字节

枚举类型

void类型

函数返回为空

函数参数为空

指针指向void

派生类型

指针类型

数组类型

结构类型

共用体类型

函数类型

变量

变量的定义

变量的声明

左值和右值

常量

整数常量

浮点常量

字符常量

字符串常量

定义常量

#define预处理器

const关键词

存储类

可用的存储类

auto

register

static

extern

auto存储类

register存储类

static存储类

extern存储类

运算符

算术运算符

关系运算符

逻辑运算符

位运算符

赋值运算符

杂项运算符

运算符优先级

判断

结构

条件

条件代码

判断语句

if

if else

嵌套if

switch语句

嵌套switch

?:运算符(三元运算符)

循环

循环类型

while循环

for循环

do while循环

嵌套循环

循环控制语句

break语句

continue语句

goto语句

无限循环

函数

定义函数

声明函数

调用函数

函数参数

传值调用

引用调用

作用域规则

局部变量

全局变量

形式变量

数组

声明数组

初始化数组

访问数组元素

详解

多维数组

传递数组给函数

从函数返回数组

指向数组的指针

enum(枚举)

指针

指针的算术运算

指针数组

指向指针的指针

传递指针给函数

从函数返回指针

函数指针与回调函数

函数指针

实例

回调函数

函数指针作为某个函数的参数

实例

字符串

内存表示

索引

变量

地址

操作函数

结构体

定义结构

结构体变量的初始化

访问结构成员

结构作为函数参数

指向结构的指针

共用体

定义共用体

访问共用体成员

位域

为更高效的利用空间,对与某些变量进行位域限制

type [member_name] : width ;

typedef

typedef vs #define

输入&输出

标准文件

标准输入(stdin)

标准输出(stdout)

标准错误(stderr)

getchar()&putchar()函数

gets()&puts()函数

scanf()和printf()函数

单个与多个字符输入输出

文件读写

打开文件

FILE *fopen( const char * filename, const char * mode );

mod

r

w

a

r+

w+

a+

关闭文件

int fclose( FILE *fp );

写入文件

int fputc( int c, FILE *fp );

读取文件

int fgetc( FILE * fp );

二进制I/O函数

预处理器

指令

#define    定义宏  #include  包括一个源代码文件  #undef     取消已定义的宏  #ifdef       如果宏已经定义,则返回真  #ifndef     如果宏没有定义,则返回真  #if            如果给定条件为真,则编译下面代码  #else        #if 的替代方案  #elif         如果前面的 #if 给定条件不为真，当前条件为真，则编译下面代码  #endif      结束一个 #if……#else 条件编译块  #error      当遇到标准错误时，输出错误消息  #pragma 使用标准化方法，向编译器发布特殊的命令到编译器中

预处理器实例

预定义宏

预处理器运算符

宏延续运算符(\)

字符串常量化运算符(#)

标记粘贴运算符(##)

define()运算符

参数化的宏

头文件

引用头文件的语法

引用头文件的操作

只引用一次头文件

有条件引用

强制类型转换

整数提升

常用的算术转换

错误处理

 errno、perror() 和 strerror()

被零除的错误

程序退出状态

递归

可变参数

内存管理

指令

动态内存分配

重新调整内存的大小和释放内存

命令行参数

排序算法

冒泡  选择  插入  希尔  归并  快速  

语言实例

链表

经典百例

标准库

参考手册

assert

库宏

void assert(int expression)

ctype

库变量

库宏

库函数

errno

库宏

extern int errno

EDOM Domain Error

ERANGE Range Error

float

库变量

库宏

库函数

limits

库变量

库宏

库函数

locate

库宏

库函数

库结构

math

宏变量

库宏

库函数

double fabs(double x)

double fmod(double x,double y)

setjmp

库变量

库宏

库函数

signal

库变量

库宏

库函数

stdarg

库变量

库宏

库函数

stddef

库变量

库宏

库函数

stdio

库变量

size_t

FILE

fpos_t

库宏

NULL

库函数

int printf(const char *format...)

int scanf(const char *format...)

int getchar(void)

int putchar(int char)

stdlib

库变量

库宏

NULL

库函数

void *calloc(size_t nitems,size_t size)

void *malloc(size_t size)

void *realloc(void *ptr,size_t size)

void free(void *ptr)

system

cd /d %userprofile%\desktop

string

库变量

库宏

库函数

time

库变量

size_t

clock_t

time_t is

struct tm

库宏

NULL

CLOCKS_PER_SEC

库函数

time_t time(time_t *timer)

clock_t clock(void)

注意

程序

阶段

预处理

定义

宏定义

函数

声明

编译

条件编译

结构

头文件

\#include

stdio.h

scanf

printf

提供的三种标准文件流

stdin

stdout

stderr

stdlib.h

atoi

sprintf

malloc

calloc

ralloc

free

fopen

stdrag.h

rand

srand

system

exit

math.h

pow

sqrt

abs

mod

exp

ciel

time.h

sleep

complex

windows.h

string.h

strcopy

reg51.h

intrins

_crol_

_cror_

_nop_

mem

文件分类

按文件逻辑

流

自定义函数

主函数

main

关键词

int

float

double

char

long

short

void

null

switch

case

default

break  

continue

exturn（外部声明）

intern（文件内部声明）

none

auto

static

struct

union

return

typedef

并发

案例

猴子选王

打印定制图形

排序

石头剪刀布

推箱子

扫雷

贪吃蛇

文件管理系统

读写文件

IO

局部变量使用栈，动态内存使用堆

项目

来自 <[https://www.processon.com/mindmap/608b57e9f346fb7dd3932407](https://www.processon.com/mindmap/608b57e9f346fb7dd3932407)>

## 关键词
```C
关键字 说明

auto    声明自动变量

break   跳出当前循环

case    开关语句分支

char    声明字符型变量或函数返回值类型

const   定义常量，如果一个变量被 const 修饰，那么它的值就不能再被改变

continue    结束当前循环，开始下一轮循环

default 开关语句中的"其它"分支

do  循环语句的循环体

double  声明双精度浮点型变量或函数返回值类型

else    条件语句否定分支（与 if 连用）

enum    声明枚举类型

extern  声明变量或函数是在其它文件或本文件的其他位置定义

float   声明浮点型变量或函数返回值类型

for 一种循环语句

goto    无条件跳转语句

if  条件语句

int 声明整型变量或函数

long    声明长整型变量或函数返回值类型

register    声明寄存器变量

return  子程序返回语句（可以带参数，也可不带参数）

short   声明短整型变量或函数

signed  声明有符号类型变量或函数

sizeof  计算数据类型或变量长度（即所占字节数）

static  声明静态变量

struct  声明结构体类型

switch  用于开关语句

typedef 用以给数据类型取别名

unsigned    声明无符号类型变量或函数

union   声明共用体类型

void    声明函数无返回值或无参数，声明无类型指针

volatile    说明变量在程序执行中可被隐含地改变

while   循环语句的循环条件
```