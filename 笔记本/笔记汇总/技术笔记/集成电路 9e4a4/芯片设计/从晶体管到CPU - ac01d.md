# 从晶体管到CPU - 简书

# [从晶体管到 CPU](https://www.jianshu.com/p/960a5fafa917)

晶体管是 CPU 中的最小组成元器件；
晶体管的组合，可以形成基本逻辑单元 (非门、与非门、或非门…)；
基本逻辑单元的组合，可以形成基本逻辑电路 (全加器、地址译码器、三态门、D 锁存器、D 触发器、移位寄存器)；
由基本逻辑电路的组合，可以形成一个最基本的概念 CPU；

## 1. 最小元器件 (晶体管 / 场效应管)

**晶体管**有 NPN 型、PNP 型
晶体管的三级分别为基极 (B)、集电极 (C)、射极 (E)
对于 NPN 型，当基极给正电流，集电极射极导通，反之断开；
对于 PNP 型，当基极给负电流，射极集电极导通，反之断开；

![https://upload-images.jianshu.io/upload_images/5953827-aade3f566a121db8.png](https://upload-images.jianshu.io/upload_images/5953827-aade3f566a121db8.png)

晶体管. png

**场效应管**有 N 型、P 型
场效应管的三级分别为控制极 (G)、源极 (Vss)、漏极 (Vdd)
对于 N 型，当控制极给高电压，源极漏极导通，反之断开；
对于 P 型，当控制极给低电压，漏极源极导通，反之断开；

![https://upload-images.jianshu.io/upload_images/5953827-4f9f191f8a0c7cf5.png](https://upload-images.jianshu.io/upload_images/5953827-4f9f191f8a0c7cf5.png)

场效应管. png

场效应管也是一种晶体管；

## 2. 基本逻辑单元

通过晶体管的组合，可以形成基本逻辑单元

### 非门 B=!A

![https://upload-images.jianshu.io/upload_images/5953827-fae4b0b38f7d1409.png](https://upload-images.jianshu.io/upload_images/5953827-fae4b0b38f7d1409.png)

非门. png

### 与非门 C=!(A&B)

![https://upload-images.jianshu.io/upload_images/5953827-497781703c1954ca.png](https://upload-images.jianshu.io/upload_images/5953827-497781703c1954ca.png)

与非门. png

### 或非门 C=!(A|B)

![https://upload-images.jianshu.io/upload_images/5953827-b94a3d16b816b639.png](https://upload-images.jianshu.io/upload_images/5953827-b94a3d16b816b639.png)

或非门. png

### 三态门

C 为 1 时输出等于输入，C 为 0 时输出为高阻状态 (可理解为空)

![https://upload-images.jianshu.io/upload_images/5953827-ba2b19f2bbcc75d3.png](https://upload-images.jianshu.io/upload_images/5953827-ba2b19f2bbcc75d3.png)

三态门. png

### 与门 A&B、或门 A|B

它们不是最简单的逻辑单元，而是组合出来的

![https://upload-images.jianshu.io/upload_images/5953827-c4f1462fd909cd33.png](https://upload-images.jianshu.io/upload_images/5953827-c4f1462fd909cd33.png)

与门 或门. png

### 异或门

同样是组合出来的

![https://upload-images.jianshu.io/upload_images/5953827-50d52daf4e145875.png](https://upload-images.jianshu.io/upload_images/5953827-50d52daf4e145875.png)

异或门. png

## 3. 基本逻辑电路

通过基本逻辑单元的组合，可以形成基本逻辑电路；

### 加法 (减法) 器

**全加器**：xyz 表示三个二进制数，cs 表示二位二进制结果

![https://upload-images.jianshu.io/upload_images/5953827-ca93393fce690091.png](https://upload-images.jianshu.io/upload_images/5953827-ca93393fce690091.png)

全加器. png

四个全加器组合，形成 4 比特的加法电路

![https://upload-images.jianshu.io/upload_images/5953827-621377bb1ee3fd6f.png](https://upload-images.jianshu.io/upload_images/5953827-621377bb1ee3fd6f.png)

加法电路. png

有了加法就有了减法，因为减法等于加上一个负数、 负数可表示为一个二进制的补码

### 译码器

地址译码器，当 A0~4 给特定值时 (地址) 输出为 1，否则为 0；
输出接三态门后，可实现类似通过内存地址取值的操作；

![https://upload-images.jianshu.io/upload_images/5953827-295413cf8c58cd2c.png](https://upload-images.jianshu.io/upload_images/5953827-295413cf8c58cd2c.png)

地址译码器. png

二四译码器，输入 AB 的不同组合，输出端依次只有一个为 0(实现了多路选择)

![https://upload-images.jianshu.io/upload_images/5953827-9a6abd5769ba5bac.png](https://upload-images.jianshu.io/upload_images/5953827-9a6abd5769ba5bac.png)

二四译码器. png

### D 锁存器、D 触发器

之前的逻辑电路输出值总是取决于当前的输入值，我们称之为组合逻辑电路；
如果输出值不是只取决于当前输入值，还取决于上一个状态的输出值，我们则称之为时序逻辑电路；**D 锁存器**：C 为 0 时 Q 和 Q 反的值不发生变化，C 为 1 时 Q 等于 D、Q 反等于 D 相反值；(保存了状态)

![https://upload-images.jianshu.io/upload_images/5953827-cca78472bd6fb326.png](https://upload-images.jianshu.io/upload_images/5953827-cca78472bd6fb326.png)

D 锁存器. png

**D 触发器**：在 D 锁存器基础上加入了根据 CLK 信号边缘触发；

![https://upload-images.jianshu.io/upload_images/5953827-ce19370947100217.png](https://upload-images.jianshu.io/upload_images/5953827-ce19370947100217.png)

D 触发器. png

![https://upload-images.jianshu.io/upload_images/5953827-d8ea36932a651e7b.png](https://upload-images.jianshu.io/upload_images/5953827-d8ea36932a651e7b.png)

D 触发器时序图. png

**移位寄存器**：将 D 触发器串行组合后，可以形成移位寄存器，依靠时钟脉冲将信号不断右移；(**实现乘除法**)

![https://upload-images.jianshu.io/upload_images/5953827-c6c2e5023eb70039.png](https://upload-images.jianshu.io/upload_images/5953827-c6c2e5023eb70039.png)

移位寄存器. png

## 4. 概念 CPU

通过基本逻辑电路，我们实现了加减、与或、左右移 (乘除)、多路选择；
利用这些基本逻辑电路，可以组合成一个概念 CPU 如下图：

![https://upload-images.jianshu.io/upload_images/5953827-f9f3b01efda21292.png](https://upload-images.jianshu.io/upload_images/5953827-f9f3b01efda21292.png)

概念 CPU.png

A、B 为两个四位二进制输入信号，同时接到四个运算电路上；
利用加法、与或、左移、右移电路，可以对 AB 进行加减乘除与或运算；(S0、S1 可以调整运算电路的运算规则)
运算结果给到多路开关，通过 S2、S3 的取值来选择输出哪种计算结果；
该电路实现了通过给定的 S0~3，可以知道取哪个计算电路的哪种计算方式来对 A、B 进行计算；
把 S0~3 的 16 种排列组合，理解为概念 CPU 的 16 条指令，A、B 理解为两个四比特的运算数，那么这就是一个四比特概念 CPU；
程序的执行，就是交替给 CPU 指令和运算数让其运算；

![https://upload-images.jianshu.io/upload_images/5953827-cfa06effd061fe37.png](https://upload-images.jianshu.io/upload_images/5953827-cfa06effd061fe37.png)

概念 CPU 指令集. png