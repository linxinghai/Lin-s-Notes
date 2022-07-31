# 详解FPGA如何实现FP16格式点积级联运算 - SoC - 半导体芯科技

Property: April 15, 2022 10:02 PM

作者：[杨宇](http://Dawson.Guo@achronix.com/)，Achronix 资深现场应用工程师

***通过使用 Achronix Speedster7t FPGA 中的机器学习加速器 MLP72，开发人员可以轻松选择浮点 / 定点格式和多种位宽，或快速应用块浮点，并通过内部级联可以达到理想性能。***

神经网络架构中的核心之一就是卷积层，卷积的最基本操作就是点积。向量乘法的结果是向量的每个元素的总和相乘在一起，通常称之为点积。此向量乘法如下所示：

![http://www.siscmag.com/upload/202008/17/202008172150396966.png](http://www.siscmag.com/upload/202008/17/202008172150396966.png)

*图 1. 点积操作。*

该总和 S 由每个矢量元素的总和相乘而成，因此

![http://www.siscmag.com/upload/202008/17/202008172155427114.png](http://www.siscmag.com/upload/202008/17/202008172155427114.png)

本文讲述的是使用 FP16 格式的点积运算实例，展示了 MLP72 支持的数字类型和乘数的范围。

此设计实现了同时处理 8 对 FP16 输入的点积。该设计包含四个 MLP72，使用 MLP 内部的级联路径连接。每个 MLP72 将两个并行乘法的结果相加（即

![http://www.siscmag.com/upload/202008/17/202008172156345401.png](http://www.siscmag.com/upload/202008/17/202008172156345401.png)

），每个乘法都是 i_a 输入乘以 i_b 输入（均为 FP16 格式）的结果。来自每个 MLP72 的总和沿着 MLP72 的列级联到上面的下一个 MLP72 块。在最后一个 MLP72 中，在每个周期上，计算八个并行 FP16 乘法的总和。

最终结果是多个输入周期内的累加总和，其中累加由 i_first 和 i_last 输入控制。 i_first 输入信号指示累加和归零的第一组输入。 i_last 信号指示要累加和加到累加的最后一组输入。最终的 i_last 值可在之后的六个周期使用，并使用 i_last o_valid 进行限定。两次运算之间可以无空拍。

**▼** **配置说明**

![http://www.siscmag.com/upload/202008/17/202008172150534995.png](http://www.siscmag.com/upload/202008/17/202008172150534995.png)

*表 1. FP16 点积配置表。*

l  端口说明

![http://www.siscmag.com/upload/202008/17/202008172151026307.png](http://www.siscmag.com/upload/202008/17/202008172151026307.png)

*表 2. FP16 点积端口说明表。*

**▼ 时序图**

![http://www.siscmag.com/upload/202008/17/202008172151117854.png](http://www.siscmag.com/upload/202008/17/202008172151117854.png)

*图 2. FP16 点积时序图。*

其中，

![http://www.siscmag.com/upload/202008/17/202008172153053055.png](http://www.siscmag.com/upload/202008/17/202008172153053055.png)

那么，以上运算功能如何对应到 MLP 内部呢？其后的细节已分为 MLP72 中的多个功能阶段进行说明。

**▼ 进位链**

首先请看下图，MLP 之间的进位链结构，这是 MLP 内部的专用走线，可以保证级联的高效执行。

![http://www.siscmag.com/upload/202008/17/202008172151215797.png](http://www.siscmag.com/upload/202008/17/202008172151215797.png)

*图 3. MLP 进位链。*

**▼ 乘法阶段**

下图是 MLP 中浮点乘法功能阶段，其中寄存器代表一级可选延迟。

![http://www.siscmag.com/upload/202008/17/202008172151351491.png](http://www.siscmag.com/upload/202008/17/202008172151351491.png)

*图 4. MLP 乘法功能阶段框图。*

MLP72 浮点乘法级包括两个 24 位全浮点乘法器和一个 24 位全浮点加法器。两个乘法器执行 A×B 和 C×D 的并行计算。加法器将两个结果相加得到 A×B + C×D。

乘法阶段有两个输出。下半部分输出可以在 A×B 或（A×B + C×D）之间选择。上半部分输出始终为 C×D。

乘法器和加法器使用的数字格式由字节选择参数以及和参数设置的格式确定。

浮点输出具有与整数输出级相同的路径和结构。MLP72 可以配置为在特定阶段选择整数或等效浮点输入。输出支持两个 24 位全浮点加法器，可以对其进行加法或累加配置。 进一步可以加载加法器（开始累加），可以将其设置为减法，并支持可选的舍入模式。

最终输出阶段支持将浮点输出格式化为 MLP72 支持的三种浮点格式中的任何一种。 此功能使 MLP72 可以外部支持大小一致的浮点输入和输出（例如 fp16 或 bfloat16），而在内部以 fp24 执行所有计算。

![http://www.siscmag.com/upload/202008/17/202008172151499548.png](http://www.siscmag.com/upload/202008/17/202008172151499548.png)

*图 5. MLP 浮点输出阶段框图。*

需要强调的是本设计输入和输出都是 FP16 格式，中间计算过程，即进位链上的 fwdo_out 和 fwdi_dout 都是 FP24 格式。具体逻辑框图如下所示：

![http://www.siscmag.com/upload/202008/17/202008172152018125.png](http://www.siscmag.com/upload/202008/17/202008172152018125.png)

*图 6. FP16 点积逻辑框图。*

MLP 内部数据流示意图：

![http://www.siscmag.com/upload/202008/17/202008172152246860.png](http://www.siscmag.com/upload/202008/17/202008172152246860.png)

*图 7. FP16 点积在 MLP 内部数据流图。*

最终 ACE 的时序结果如下：

![http://www.siscmag.com/upload/202008/17/202008172152428831.png](http://www.siscmag.com/upload/202008/17/202008172152428831.png)

*（表 3.）*

声明：本网站部分文章转载自网络，转发仅为更大范围传播。 转载文章版权归原作者所有，如有异议，请联系我们修改或删除。联系邮箱：viviz@actintl.com.hk， 电话：0755-25988573 [http://www.siscmag.com/news/show-3554.html](http://www.siscmag.com/news/show-3554.html)