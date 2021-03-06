# 计算机系统概述

## 计算机系统简介

-   分类
    -   专用计算机 _嵌入式系统_
    -   通用计算机 _普通 PC 机_
-   通用计算机类型
-   计算机系统
    -   硬件+软件
    -   软硬件关系
        -   硬件 物质基础
        -   软件 硬件功能的完善和补充
-   计算机硬件和软件的逻辑等价
    -   许多功能既可以用硬件实现，也可以在基本硬件的支持下，利用软件实现
    -   软硬件的功能分配，随技术发展二变化，没有固定的模式
    -   软件固化：将软件的一些功能固化地保存在只读存储器中，称为*固化*
        -   功能上是软件，形态上是硬件
        -   一些系统软件的核心部分，常被固化在存储芯片中

## 计算机系统的层次结构

-   现代计算机的解题处理过程
    1. 用户描述求解过程
    2. 程序&数据$\to$计算机，翻译为机器语言程序
    3. 计算机运行机器语言程序，输出结果
-   $应用语言\to 高级语言\to 汇编语言\to 操作系统 \stackrel{软件|硬件}{\longrightarrow}机器语言\to 微指令系统$

# 计算机的基本组成

## 计算机的硬件组成

-   计算机硬件五大组成部件

    1. 存储器
       存放数据&程序
    2. 运算器
       完成算术运算&逻辑运算，暂存中间结果
    3. 输入设备
       将人们熟悉的信息形式转换成机器能识别的形式
    4. 输出设备
       将机器运算结果转换成人们熟悉的信息形式展示出来
    5. 控制器
       控制、指挥程序和数据的输入、运行及处理运算结果

-   冯·诺伊曼计算机组成结构（也称普林斯顿结构）

    -   五大组成部件 以运算器为中心
    -   数据、指令用二进制数表示，同等地位存放于存储器中，按地址访问
    -   指令由操作码和地址码组成，在存储器中按顺序存放

-   哈佛结构

    -   将指令、数据分开存储

-   区别

    1. 指令、数据是否分别存储
    2. 是否使用两条独立的总线，分别作为 CPU 与每个存储器的专用通信通道，总线毫无关联
    3. 哈佛结构多用于嵌入式应用中

-   现代计算机的组成结构

    -   以**存储器**为中心
    -   $\underline{运算器}$、$\underline{控制器}$在$\underline{逻辑关系}$和$\underline{电路结构}$联系紧密，集成在同一芯片上，称为**中央处理器 CPU**
    -   输入、输出设备：I/O 设备
    -   现代计算机三大组成部件
        CPU + 主存储器 $\to$ 主机
        I/O 设备 $\to$ 外部设备

-   运算器

    -   常称为 算术逻辑运算部件 ALU
    -   运算数据格式
        -   二进制数
        -   长度一般为$2^n$
    -   运算器至少包括 3 个寄存器
        1. ACC 累加器
        2. MQ 乘商寄存器
        3. X 操作数寄存器
    -   数据传送
        -   $ACC\to MDR$
        -   $MDR\to ACC、MQ、X$
    -   四则运算过程 表示规定
        -   M：存储器地址
            [M]：地址中内容
            X/MQ/ACC：寄存器
            [X]/[MQ]/[ACC]：寄存器中内容
        1. 加法
           $[M]\to X$
           $[ACC]+[X]\to ACC$
        2. 减法
           $[M]\to X$
           $[ACC]-[X]\to ACC$
        3. 乘法
           $[M]\to MQ$
           $[ACC]\to X$
           $0\to ACC$
           $[X]*[MQ]\to ACC//MQ$
        4. 除法
           $[M]\to X$
           $[ACC]/[X]\to MQ$
           余数 R 在 ACC 中

-   控制器

    -   控制计算机有序工作
    -   基本任务
        1. 取指过程：取出指令。
        2. 分析过程：对指令进行分析，确定要完成的操作(操作码) ，并按寻址特征找出操作数的地址。
        3. 执行过程：根据操作数地址及指令的操作码，完成相应的操作。
    -   控制器组成
        1. 程序计数器 PC：用于存放当前将要执行的指令，具有自动加 1 的功能，能够自动形成下一条指令的地址
        2. 指令寄存器 IR：存放 CPU 当前正在执行的指令内容
        3. 控制单元 CU：分析当前指令所要完成的操作，并发出各种微操作的命令序列
    -   CPU 功能与指令的执行过程
        -   功能
            -   算术逻辑运算
            -   指令译码、执行
            -   数据暂存
            -   与 MEM、 I/O 交换数据
            -   提供整个系统的定时和控制
            -   响应中断请求
        -   过程
            1. 取指
            2. 译码
            3. 取操作数
            4. 执行
            5. 写回
    -   **指令**：计算机实现某种操作(控制或运算)的一条代码
        -   指令系统
            -   一台计算机通常有几十种基本指令，它们构成了该计算机的指令系统
            -   指令系统是衡量计算机性能的重要标志

-   存储器

    -   功能 保存或“记忆”解决问题所需的数据和解题方法步骤
    -   组成
        $存储体\leftarrow存储单元\leftarrow存储元件$
        1. 存储元件，也称存储元，每个能存储一位二进制代码 0 或 1
        2. 存储单元，可存储一串二进制数，称为一个存储字(字节)，其位数称为**存储字长**
        3. 存储字代表的二进制码，可以是数值、字符等，也可以表示指令
        4. 存储地址 对每个存储单元进行编号，其编号称为该存储单元的地址
    -   组织
        1. 存储单元按**字节**或**字**寻址
        2. 程序和数据顺序存放
        3. 读写操作以数据总线宽度为单位
    -   主存储器工作方式
        1. 按存储单元的地址号来实现对存储字各位的写入和读出——按地址存取方式(访存)
        2. 寄存器
            - MAR(Memory Address Register)
              存储器地址寄存器，存放要访问的存储单元的地址，其位数对应存储单元的个数
            - MDR(Memory Data Register)
              存储器数据寄存器，存放从某个存储单元取出的或准备往某个存储单元存入的内容，其位数与存储字长相等

-   I/O 设备

-   总线
    构成计算机系统的骨架，是计算机各个组成部件间进行数据传送的公用通路
    -   从连接角度看，可以分为**内部总线**、**系统总线**和**I/0 总线**
    -   从功能角度看，可以分为**数据总线**、**地址总线**和**控制总线**

## 计算机组成与计算机体系结构

-   计算机体系结构 - 程序员可见的机器属性，即概念性的结构与功能特性 - 机器属性包括指令集、数据类型、存储器寻址技术、 I/O 机制等

-   计算机组成

    -   计算机体系结构的逻辑实现
    -   包含实际机器的数据流和控制流的组成和逻辑设计等
    -   着眼于物理机器内部各事件的排序方式与控制方式，各部件的功能以及相互间的联系

-   计算机体系结构的属性
    1. **数据表示** 硬件能直接辨识和操作的数据类型和格式
    2. **寻址方式** 最小可寻址单位、寻址方式的种类、地址运算
    3. **寄存器组织** 操作寄存器、变址寄存器、控制寄存器及专用寄存器的定义、数量和使用规则
    4. **指令系统** 机器指令的操作类型、格式、指令间排序和控制机构
    5. **存储系统** 最小编址单位、编址方式、主存容量、最大可编址空间
    6. **输入输出结构** 输入输出的连接方式、处理机/存储器与输入输出设备间的数据交换方式、数据交换过程的控制
    7. **中断机构** 中断类型、中断级别，以及中断响应方式等
    8. **信息保护** 信息保护方式、硬件信息保护机制

## 计算机的软件组成

-   用于一台计算机的各种程序，统称为这台计算机的程序或软件系统
-   分类
    -   系统软件
        1.  各种服务程序：诊断程序、调试程序、标准函数库等
        2.  语言处理程序：汇编器、编译器等
        3.  操作系统
        4.  数据库管理系统
    -   应用软件

# 计算机硬件性能指标

## 机器字长

-   CPU 一次能处理的二进制数据的位数
    -   通常与 CPU 的寄存器位数有关，也反映运算部件和数据总线的位数
    -   影响运算速度
    -   影响计算精度
    -   影响硬件成本

## 存储容量

-   存储器中所有存储单元的总位数
    -   主存容量+辅存容量
    -   存储容量=存储单元个数$\times$存储字长
        -   存储器的地址寄存器 MAR 的位数反映了存储单元个数
        -   存储器的数据寄存器 MDR 的位数反映了**存储字长**
    -   存储容量表示
        -   字节：一字节 1B=8 位二进制数
    -   数据通路宽度
        -   数据总线一次能并行传送的信息的位数
        -   影响计算机的有效处理速度
        -   CPU 外部 CPU 内部
            -   **内部数据通路宽度** 一般等于机器字长，即内部数据线的位数
            -   **外部数据通路宽度** 一般等于系统数据总线的位数，即 CPU 与主存、 I/O 设备之间一次数据传送的信息位数，即**数据字长**
    -   字 不同机器其字的位数可能不一样，但一定是字节的倍数
    -   存储器带宽
        单位时间内从存储器读出的二进制数信息量，一般用 B/s 表示

## 运算速度

-   影响因素多，如机器主频、操作类型、主存速度
-   基准程序法(benchmark)
    -   考虑 CPU、I/O 结构、操作系统、编译器效率等
    -   评价计算机的实际工作能力
-   常用测试程序
    1. 真实程序 存在移植带来问题
    2. 核心程序 真实程序中短但关键的代码
    3. 合成测试程序
    4. 测试程序组 选择一组各方面由代表性的测试程序，组成一个通用的测试程序集合
-   基准测试套
    1. Dhrystone
        - 整数测试程序
        - 适于比较同一家族的机器
    2. Linpack
        - 测试向量性能和高速缓存性能
    3. Whetstone
        - 测试浮点操作、整数计算和功能调用等性能
    4. TPC(Transaction Processing Council)
        - 计算机(服务器)事务处理性能
    5. SPEC System Performance Evaluation Cooperative
-   早期衡量运算速度的普通方法：完成一次加/乘法的时间
    1. CPI (Cycle Per Instruction)
        - 指令周期：执行一条指令所需平均时钟周期数
            $$
            CPI=\frac{执行程序所需CPU时钟周期数}{程序包含的指令条数}
            $$
    2. MIPS (Million Instruction Per Second)
        - 百万条指令每秒：单位时间内执行指令数
            $$
            MIPS=\frac{程序的指令条数}{程序的执行时间\times 10^6}
            $$
    3. MFLOPS (Million Floating Point Operation Per Second)
        - 百万次浮点操作每秒：用来衡量及其浮点运算的性能
            $$
            MFLOPS=\frac{程序的浮点操作次数}{程序的执行时间\times 10^6}
            $$
-   详细分析 CPU 的性能
    -   时钟频率(f)：与实现技术和工艺有关，单位 MHz
        程序执行的 CPU 时间$T_{CPU}=\frac{CLK}{f}$
    -   程序执行过程中所处理的指令数：IC
    -   每条指令执行所需要的时钟周期数：CPI (Cycle Per Instruction)
        $$
        CPI=\frac{CLK}{IC}
        $$
-   CPU 性能公式&体系结构

    $$
    T_{CPU}=\frac{CPI\times IC}{f}=CPI\times IC\times T_{CLK}
    $$

    -   时钟频率(f)：计算机实现技术、生产工艺和计算机组织。
    -   指令的平均时钟周期数(CPI)：计算机组织和计算机指令集的结构。
    -   程序的指令数(IC)：计算机指令集的结构和编译技术。
    -   假设计算机系统有 n 种指令，其中第 i 种指令的处理时间为$CPI_i$ ，在程序中第 i 种指令出现的次数为$IC_i$，CLK 表示总指令数。

        $$
        T_{CPU}=CLK/f\\
        CLK=\sum (IC_i\times CPI_i)\\
        T_{CPU}=\sum (IC_i\times CPI_i)/f\\
        =\sum(IC_i\times CPI_i)\times T_{CLK}\\
        \\
        CPI=CLK/IC\quad(总指令数/总指令出现次数\quad每个指令产生的指令数很可能不是1)\\
        =\sum(IC_i\times CPI_i)/IC\\
        =\sum[(IC_i/IC)\times CPI_i]
        $$

        其中，$IC_i/IC$反映了第 i 种指令在程序所占的比例。

    -   响应时间
    -   吞吐率
    -   可靠性
    -   可用率

## 计算机硬件性能指标

1. 执行时间（CPU 时间、 Elapsed Time）
2. 峰值速度（Peak Performance）
3. 负载（load）
4. 开销 （Overhead）
5. 利用率（Utilization Ratio）
6. 饱和性能（Saturate Performance）
7. 带宽（Bandwidth）
8. 延迟（Latency）
9. 加速比（Speedup）
10. 效率（Efficiency）

# 计算机/CPU 发展历史

# Amdahl 定律

$$
系统加速比=\frac{系统性能_{改进后}}{系统性能_{改进前}}=\frac{总执行时间_{改进前}}{总执行时间_{改进后}}
$$

记$T_o$为加速前运行时间，$T_e$为加速后运行时间，$T_1$为加速前，可加速部分运行时间，$T_2$为加速后，可加速部分运行时间，$f_e=\frac{T_1}{T_o}$为可加速部分所占比例，$S_e=\frac{T_1}{T_2}$为加速比。从而有

$$
\begin{aligned}
T_e&=T_o-T_1+T_2\\
&=T_o(1-\frac{T_1}{T_o}+\frac{T_1/T_o}{T_1/T_2})\\
&=T_o(1-f_e+\frac{f_e}{S_e})
\end{aligned}
$$

所以总加速比

$$
\begin{aligned}
S&=\frac{T_o}{T_e} \\
&=\frac{1}{1-f_e+\frac{f_e}{S_e}}
\end{aligned}
$$

# 芯片制作

$$
\begin{aligned}
集成电路成本&=\frac{晶片成本+晶片测试成本+封装成本}{最终成品率}\\
\\
晶片成本&=\frac{晶圆成本}{每块晶圆上的晶片数\times晶片成品率}\\
\\
每块晶圆上的晶片数&=\frac{晶圆面积}{晶片面积}-\frac{\pi\times晶圆直径}{\sqrt{2\times晶片面积}} \\
\\
晶片成品率&=晶圆成品率\times(1+\frac{疵点密度\times晶片面积}{\alpha})^{-\alpha}\\
\alpha=3\sim 4
\end{aligned}
$$
