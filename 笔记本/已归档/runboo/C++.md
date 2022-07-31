
#runoob 
[**C++ 开发从入门到精通**](笔记本/已归档/技术/其他笔记/杂七杂八-待整理%20ed340/C++%20开发从入门到%20f2f69.md)


C++
C
面向对象
抽象
类
封装
继承
多态
容器
模板
泛型
STL
RTTI
元编程

## 关键词
```C++
asm 
else    
new 
this

auto    
enum    
operator    
throw

bool    
explicit    
private 
true

break   
export  
protected   
try

case    
extern  
public  
typedef

catch   
false   
register    
typeid

char    
float   
reinterpret_cast    
typename

class   
for 
return  
union

const   
friend  
short   
unsigned

const_cast  
goto   
signed  
using

continue    
if  
sizeof  
virtual

default 
inline  
static  
void

delete  
int 
static_cast 
volatile

do  
long    
struct  
wchar_t

double  
mutable 
switch  
while

dynamic_cast    
namespace   
template
1. asmasm (指令字符串)：允许在 C++ 程序中嵌入汇编代码。

2. autoauto（自动，automatic）是存储类型标识符，表明变量"自动"具有本地范围，块范围的变量声明（如for循环体内的变量声明）默认为auto存储类型。

3. boolbool（布尔）类型，C++ 中的基本数据结构，其值可选为 true（真）或者 false（假）。C++ 中的 bool 类型可以和 int 混用，具体来说就是 0 代表 false，非 0 代表 true。bool 类型常用于条件判断和函数返回值。

4. breakbreak（中断、跳出），用在switch语句或者循环语句中。程序遇到 break 后，即跳过该程序段，继续后面的语句执行。

5. case用于 switch 语句中，用于判断不同的条件类型。

6. catchcatch 和 try 语句一起用于异常处理。

7. charchar（字符，character）类型，C++ 中的基本数据结构，其值一般为 0~255 的 int。这 256 个字符对应着 256 个 ASCII 码。char 类型的数据需要用单引号 ' 括起来。

8.classclass（类）是 C++ 面向对象设计的基础。使用 class 关键字声明一个类。

9. constconst（常量的，constant）所修饰的对象或变量不能被改变，修饰函数时，该函数不能改变在该函数外面声明的变量也不能调用任何非const函数。在函数的声明与定义时都要加上const，放在函数参数列表的最后一个括号后。在 C++ 中，用 const 声明一个变量，意味着该变量就是一个带类型的常量，可以代替 #define，且比 #define 多一个类型信息，且它执行内链接，可放在头文件中声明；但在 C 中，其声明则必须放在源文件（即 .C 文件）中，在 C 中 const 声明一个变量，除了不能改变其值外，它仍是一具变量。如:const double pi(3.14159);或 const double pi = 3.141592653589793 3.14159;

10. const_cast用法：const_cast<type_id> (expression)该运算符用来修改类型的 const 或 volatile 属性。除了 const 或 volatile 修饰之外， type_id 和 expression 的类型是一样的。常量指针被转化成非常量指针，并且仍然指向原来的对象；常量引用被转换成非常量引用，并且仍然指向原来的对象；常量对象被转换成非常量对象。

11. continuecontinue（继续）关键字用于循环结构。它使程序跳过代码段后部的部分，与 break 不同的是，continue 不是进入代码段后的部分执行，而是重新开始新的循环。因而它是"继续循环"之意，不是 break（跳出）。

12. defaultdefault（默认、缺省）用于 switch 语句。当 switch 所有的 case 都不满足时，将进入 default 执行。default 只能放在 switch 语句所有的 case 之后，并且是可选的。

13. deletedelete（删除）释放程序动态申请的内存空间。delete 后面通常是一个指针或者数组 []，并且只能 delete 通过 new 关键字申请的指针，否则会发生段错误。

14. dodo-while是一类循环结构。与while循环不同，do-while循环保证至少要进入循环体一次。

15. doubledouble（双精度）类型，C++ 中的基本数据结构，以双精度形式存储一个浮点数。

16. dynamic_castdynamic_cast（动态转换），允许在运行时刻进行类型转换，从而使程序能够在一个类层次结构安全地转换类型。dynamic_cast 提供了两种转换方式，把基类指针转换成派生类指针，或者把指向基类的左值转换成派生类的引用。

17. elseelse 紧跟在 if 后面，用于对 if 不成立的情况的选择。

18. enumenum（枚举）类型，给出一系列固定的值，只能在这里面进行选择一个。

19. explicitexplicit（显式的）的作用是"禁止单参数构造函数"被用于自动型别转换，其中比较典型的例子就是容器类型。在这种类型的构造函数中你可以将初始长度作为参数传递给构造函数。

20. export为了访问其他编译单元（如另一代码文件）中的变量或对象，对普通类型（包括基本数据类、结构和类），可以利用关键字 extern，来使用这些变量或对象时；但是对模板类型，则必须在定义这些模板类对象和模板函数时，使用标准 C++ 新增加的关键字 export（导出）。

21. externextern（外部的）声明变量或函数为外部链接，即该变量或函数名在其它文件中可见。被其修饰的变量（外部变量）是静态分配空间的，即程序开始时分配，结束时释放。用其声明的变量或函数应该在别的文件或同一文件的其它地方定义（实现）。在文件内声明一个变量或函数默认为可被外部使用。在 C++ 中，还可用来指定使用另一语言进行链接，这时需要与特定的转换符一起使用。目前仅支持 C 转换标记，来支持 C 编译器链接。使用这种情况有两种形式：extern "C" 声明语句extern "C" { 声明语句块 }

22. falsefalse（假的），C++ 的基本数据结构 bool 类型的值之一。等同于 int 的 0 值。

23. floatfloat（浮点数），C++ 中的基本数据结构，精度小于 double。

24. forfor 是 C++ 中的循环结构之一。

25. friendfriend（友元）声明友元关系。友元可以访问与其有 friend 关系的类中的 private/protected 成员，通过友元直接访问类中的 private/protected 成员的主要目的是提高效率。友元包括友元函数和友元类。

26. gotogoto（转到），用于无条件跳转到某一标号处开始执行。

27. ifif（如果），C++ 中的条件语句之一，可以根据后面的 bool 类型的值选择进入一个分支执行。

28. inlineinline（内联）函数的定义将在编译时在调用处展开。inline 函数一般由短小的语句组成，可以提高程序效率。

29. intint（整型，integer），C++ 中的基本数据结构，用于表示整数，精度小于 long。

30. longlong（长整型，long integer），C++ 中的基本数据结构，用于表示长整数。

31. mutablemutable（易变的）是 C++ 中一个不常用的关键字。只能用于类的非静态和非常量数据成员。由于一个对象的状态由该对象的非静态数据成员决定，所以随着数据成员的改变，对像的状态也会随之发生变化。如果一个类的成员函数被声明为 const 类型，表示该函数不会改变对象的状态，也就是该函数不会修改类的非静态数据成员。但是有些时候需要在该类函数中对类的数据成员进行赋值，这个时候就需要用到 mutable 关键字。

32. namespacenamespace（命名空间）用于在逻辑上组织类，是一种比类大的结构。

33. newnew（新建）用于新建一个对象。new 运算符总是返回一个指针。由 new 创建34. operatoroperator（操作符）用于操作符重载。这是 C++ 中的一种特殊的函数。

35. privateprivate（私有的），C++ 中的访问控制符。被标明为 private 的字段只能在本类以及友元中访问。

36. protectedprotected（受保护的），C++ 中的访问控制符。被标明为 protected 的字段只能在本类以及其继承类和友元中访问。

37. publicpublic（公有的），C++ 中的访问控制符。被标明为 public 的字段可以在任何类

38.registerregister（寄存器）声明的变量称着寄存器变量，在可能的情况下会直接存放在机器的寄存器中；但对 32 位编译器不起作用，当 global optimizations（全局优化）开的时候，它会做出选择是否放在自己的寄存器中；不过其它与 register 关键字有关的其它符号都对32位编译器有效。

39. reinterpret_cast用法：reinpreter_cast<type-id> (expression)type-id 必须是一个指针、引用、算术类型、函数指针或者成员指针。它可以把一个指针转换成一个整数，也可以把一个整数转换成一个指针（先把一个指针转换成一个整数，在把该整数转换成原类型的指针，还可以得到原先的指针值）。

40. returnreturn（返回）用于在函数中返回值。程序在执行到 return 语句后立即返回，return 后面的语句无法执行到。

41. shortshort（短整型，short integer），C++ 中的基本数据结构，用于表示整数，精度小于 int。

42. signedsigned（有符号），表明该类型是有符号数，和 unsigned 相反。数字类型（整型和浮点型）都可以用 signed 修饰。但默认就是 signed，所以一般不会显式使用。

43. sizeof由于 C++ 每种类型的大小都是由编译器自行决定的，为了增加可移植性，可以用 sizeof 运算符获得该数据类型占用的字节数。

44. staticstatic（静态的）静态变量作用范围在一个文件内，程序开始时分配空间，结束时释放空间，默认初始化为 0，使用时可改变其值。静态变量或静态函数，只有本文件内的代码才可访问它，它的名字（变量名或函数名）在其它文件中不可见。因此也称为"文件作用域"。在 C++ 类的成员变量被声明为 static（称为静态成员变量），意味着它被该类的所有实例所共享，也就是说当某个类的实例修改了该静态成员变量，其修改值为该类的其它所有实例所见；而类的静态成员函数也只能访问静态成员（变量或函数）。类的静态成员变量必须在声明它的文件范围内进行初始化才能使用，private 类型的也不例外。

45. static_cast用法：static_cast < type-id > ( expression ) 该运算符把 expression 转换为 type-id 类型，
```