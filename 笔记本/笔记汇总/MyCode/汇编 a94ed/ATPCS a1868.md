# ATPCS

r15  pc    程序计数器
r14  lr    连接寄存器
r13  sp    数据栈指针
r12  ip    子程序内部调用的scratch寄存器
r11  v8     arm状态局部变量寄存器
r10  v7 s1  在支持数据栈检查的atpcs中为数据栈限制指针
r9   v6 sb  在支持rwpi的atpcs中的静态基址寄存器
r8   v5
r7   v4 wr  thumb状态工作寄存器
r6   v3
r5   v2
r4   v1
r3   a4     参数/结果scratch寄存器
r2   a3
r1   a2
r0   a1