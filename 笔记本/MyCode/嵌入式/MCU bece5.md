# MCU

- [[笔记本/MyCode/嵌入式/单片机]]
    
    优
    
    结构简单
    
    体积小
    
    价格低
    
    功耗低
    
    开发时间短
    
    有诸多现成接口
    
    I2C,SPI,AD,PWM
    
    缺
    
    速度低
    
    十几兆到百兆
    
    接口不够丰富
    
    没有USB OTG,网口,MIPI,SATA等
    
    总
    
    适合
    
    控制
    
    不适合
    
    算法
    
    数据传输
    
    高速数据处理
    
- [[DSP]]
    
    数字滤波器
    
    高吞吐量
    
    哈弗结构
    
    高处理速度
    
    主频高
    
    硬件卷积运算
    
    累加器
    
    硬件乘法器
    
    桶形位移寄存器
    
    总
    
    适合
    
    处理单路串行信号
    
    运行DSP算法
    
    不适合
    
    控制
    
- [[ARM]]
    
    优
    
    能装OS
    
    线程调度
    
    结构丰富
    
    以太网,USB,MIPI,SATA,只要OS支持
    
    配置灵活
    
    CPU
    
    单片机
    
    视频解决方案
    
    缺
    
    软件开发门槛高
    
    器件更加复杂
    
    体积大
    
    价格高
    
    功耗高
    
    总
    
    适合
    
    数据处理
    
    数据传输
    
    CPU
    
    不适合
    
    ?
    
- [[笔记本/已归档/芯片设计/FPGA]]
    
    集成元件库
    
    导线(wire)
    
    寄存器(reg)
    
    乘法器
    
    时钟管理器(PLL,DCM,MMCM)
    
    存储器(RAM,双口RAM,FIFO)
    
    存储控制器(DDR2,3,4)
    
    高速串行口(光纤,PCIe,SATA)
    
    CPU
    
    单片机(软)
    
    Microblaze(TM)
    
    x86(硬)
    
    IBM PowerPC
    
    ARM(硬)
    
    7系列以后(Zync)
    
    AD转换器
    
    开发方法
    
    硬件描述语言HDL,Verilog
    
    开发套机画电路
    
    综合
    
    把HDL转成原理图
    
    实现
    
    把原理图变成电路图
    
    方向
    
    逻辑开发
    
    时序发生
    
    DSP开发
    
    雷达
    
    嵌入式开发
    
    ARM+处理电路
    
    优点
    
    One chip to rule them all
    
    缺点
    
    价格高
    
    结构不丰富
    
    开发门槛高,周期长
    
    外围器件多,PCB设计复杂
    
    体积大,功耗高
    
    总结
    
    适合
    
    并行高速信号处理
    
    芯片设计前期验证
    
    不值得流片的高端设计
    
    不适合
    
    低成本
    

总结

应用场景

单片机

白色家电

DSP

视频直播

ARM

统揽天下

FPGA

芯片验证,高端应用

发展方向

单片机

精简的ARM-STM32-ESP32

DSP

加了DSP硬件的ARM

ARM9(哈弗结构)

TI的DSP集成C-M4核

ARM

加了各种专用电路的ARM(SoC)

FPGA

带了可编程电路的ARM

学习线路

简单的单片机

ATMEGA328P

STM32系列

ESP32系列

STM32+RTOS

ARM处理器+Linux

[关于MCU](https://www.kdocs.cn/view/l/cp10f8UIR77L)

C51

K210

树莓派

ESP32

STM32

[按键消抖](https://blog.csdn.net/xiaogu0322/article/details/78595672)

_ASM{}

_ASM{
PUSH{R0,R1,LR}
LDR
STR
POP{R0,R1,PC}
}

[多功能按键](https://blog.csdn.net/m0_46704668/article/details/113360878?spm=1001.2101.3001.6650.15&utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromBaidu%7Edefault-15.no_search_link&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromBaidu%7Edefault-15.no_search_link)

消抖

单点

多点

长摁

[随笔分类 - 嵌入式开发--JZ2440/IMX6ULL](https://www.cnblogs.com/yangguang-it/category/987820.html)