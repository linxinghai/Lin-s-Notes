# System Verilog
(SystemVerilog为Verilog-2001标准提供了一系列的扩展。这些扩展使得大型设计的建模和验证更加容易。)
```verilog
program automatic assoc_text();
    int assoc[string];

    initial begin
        assoc["spuer"] = 1;
        assoc["special"] = 2;
        assoc["offer"] = 3;

        foreach(assoc[i]) begin
            $display("assoc[%c]" = %0d",i,assoc[i]);
        end
    end
endprogram
//result:assoc[offer]=3,assoc[special]=1,assoc[super]=2
```

```verilog
package uvm_pkg
    `include "dpi/uvm_dpi.svh"
endpackage
`endif
```

Verilog 基础

(C语言数据类型,结构,压缩,非压缩数组,接口,断言)
扩展

接口

全局声明和语句

时间单位和精度

抽象数据类型

有符号和无符号限定符

用户定义的类型

枚举类型

结构体和联合体

数组

在未命名的块中声明

常量

可重定义的数据类型

模块端口连接

字母值

强制类型转换

操作符

唯一性和优先级决定语句

底部检测的循环

跳转语句

块名字和语句标签

对事件控制的增强

新的过程

动态过程

任务和函数增强

连续赋值的增强

$bit系统函数

\`define的增强

状态机建模

断言