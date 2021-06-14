# 概率论发展简史

# 概率论的几个基本概念

## 1. 随机试验和随机事件

-   随机现象：观测结果不能预先确定，是多种可能结果之一。
-   随机试验：随机现象的实现和对他某个特征的观测。
-   **定义** 基本事件：随机试验中的每个单一结果。
-   **定义** 随机事件：简称事件，由一个或若干个基本事件组成。
-   **定义** 样本空间：随机试验中所有基本事件构成的集合，通常用$\Omega$或 S 表示。
-   **定义**
    必然事件($\Omega$)：在试验中一定会发生的事件。
    不可能事件($\phi$)：在试验中不可能发生的事件。

## 2. 事件的运算

1. 子事件($A\subset B$)：事件 A 发生蕴含事件 B 一定发生，则事件 A 称为事件 B 的子事件，记为$A\subset B$。若$A \subset B$且$B\subset A$，则称事件 A 与事件 B 相等，记为 A=B。
2. 事件的和($A\cup B$)：事件 A 和事件 B 中至少有一个发生，这一事件称为事件 A 和事件 B 的和，记为$A\cap B$.
3. 事件的积($A\cap B$)：事件 A 和事件 B 中同时发生，这一事件称为事件 A 和事件 B 的积，记为$A\cap B$.
4. 对立事件($A_c或\bar{A}$)：A 不发生，这一事件称为事件 A 的对立事件(或余事件).
5. 事件的差($A-B$)：事件 A 发生而事件 B 不发生，这一事件称为事件 A 和事件 B 的差，记为$A-B$，或等价的$AB^c$.
6. De Morgan 对偶法则：
    $$
    \overline{A\cup B}=\bar{A}\cap\bar{B},\\
    \overline{A\cap B}=\bar{A}\cup\bar{B},
    $$
    可以推广到 n 个事件：
    $$
    \overline{\bigcup_{i=1}^n A_i}=\bigcap_{i=1}^n\overline{A_i}\\
    \overline{\bigcap_{i=1}^n A_i}=\bigcup_{i=1}^n\overline{A_i}
    $$

## 3. 概率的定义及性质

1. 概率的定义

    1. 古典概型
       1. 有限性
       2. 等可能性

    2. 概率的统计定义

        把含有事件 A 的随机试验独立重复做 n 次，设事件 A 发生了$n_A$次，称比值$\frac{n_A}{n}$为事件 A 发生的频率，当 n 越来越大时，频率会在某个值 p 附近波动，且波动越来越小，这个值 p 就定义为事件 A 的概率。

    3. 主观概率

    4. 概率的公理化定义

        1. （非负性）设 A 是随机事件，则$0\leq P(A)\leq 1$

        2. （规范性）设$\Omega$为必然事件，则$P(\Omega)=1$

        3. （可加性）若事件 A、B 不相容，则$P(A\cup B)=P(A)+P(B)$

            对于无穷个事件，若事件互不相容，则$P(\bigcup_{i=1}^{\infty}A_i)=\sum_{i=1}^{\infty}P(A_i)$

    5. 一些公式

        1. 若$A\subset B$，则$P(B-A)=P(B)-P(A)$

        2. $$
           P(A+B)=P(A)+P(B)-P(AB)\\
           P(A+B+C)=P(A)+P(B)+P(C)-P(AB)-P(AC)-P(BC)+P(ABC)
           $$

2. 古典概率计算的例子

    - 例
      甲乙约定 1~2 点之间相见，每人等 10 分钟，求两人相遇的概率。
      用面积表示概率

## 4. 条件概率

1.  **定义** $P(A|B)=\frac{P(AB)}{P(B)}$，称为 在给定 B 的条件下，A 的条件概率
2.  $P(*|B)是一个概率$
    $P(\omega |B)=1$
    $P(A|B)\ge 0$
3.  若${A_i}$互斥，则

    $$
    \begin{aligned}
    P(\sum A_i|B)&=\frac{P((\sum A_i)\cap B)}{P(B)}=\frac{P(\sum(A_i B))}{P(B)}\\
    &=\frac{\sum P(A_i B)}{P(B)}=\sum P(A_i|B)
    \end{aligned}
    $$

    -   推论
        1. $P(A|B)=1-P(\bar{A}|B)$
        2. $P(A_1+A_2|B)=P(A_1|B)+P(A_2|B)-P(A_1 A_2|B)$

4.  乘法定理

    -   $$
        P(AB)=P(A|B)P(B)
        $$
    -   推广到 n 个事件
        $$
        P(A_1 A_2\dots A_n)=P(A_1)P(A_2|A_1)\dots P(A_n|A_1 \dots A_{n-1})
        $$

## 5. 全概率公式和 Bayes 公式

1. 全概率公式
    - $$
      P(A)=P(A|B)P(B)+P(A|\bar{B})P(B)
      $$
    - **定义** 设$B_1,B_2,\dots B_n$是样本空间$\Omega$中的两两不相容的一组事件，即$B_i B_j=\empty,i\neq j$，且满足$\bigcup_{i=1}^n B_i=\Omega$，则称$B_1,B_2,\dots B_n$是样本空间$\Omega$的一个分割(又称完备事件群，partition)。
    - 设${B_1,B_2,\dots B_n}$是样本空间$\Omega$的一个分割，A 为$\Omega$中的一个事件，则
        $$
        P(A)=\sum_{i=1}^n P(A|B_i)P(B_i)
        $$
2. Bayes 公式
   设${B_1,B_2,\dots B_n}$是样本空间$\Omega$的一个分割，A 为$\Omega$中的一个事件，$P(B_i)>0,i=1,2,\dots,n,P(A)>0$，则
    $$
    P(B_i|A)=\frac{P(A|B_i)P(B_i)}{\sum_{j=1}^n P(A|B_j)P(B_j)}(=\frac{P(AB_i)}{P(A)})
    $$

## 6. 事件的独立性

1.  定义
    设 A、B 是两个事件，若满足$P(AB)=P(A)P(B)$，则称 A、B 相互独立。

2.  定义
    设$A_1,A_2,...A_n$是 n 个事件，以$\tilde{A_i}$表示$A_i$或$\bar{A_i}$之一，若满足
    $$
    P(\tilde{A_1}\tilde{A_2}...\tilde{A_n})=P(\tilde{A_1})P(\tilde{A_2})...P(\tilde{A_n})
    $$
    则称事件列$A_1,A_2,...A_n$相互独立。
    进而有
    $$
    P(A_{i_1}A_{i_2}...A_{i_k})=P(A_{i_1})P(A_{i_2})...P(A_{i_k})\quad(其中i_1,i_2...i_k\in \{1,2...n\})
    $$
    > 独立&互斥
    > 独立：$P(AB)=P(A)P(B)$
    > 互斥：$P(AB)=0$
    > A、B 无法同时独立&互斥，否则有$0=P(AB)=P(A)P(B)$，从而$P(A)=0或P(B)=0$，即其中一个是不可能事件，继续讨论没有意义。
3.  性质
    1.  若一列事件独立，则将其中任何一部分换成对立事件时，所得事件仍相互独立。
    2.  若一列事件独立，则它的任一部分也独立。
