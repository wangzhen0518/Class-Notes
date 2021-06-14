# 函数的基本概念

1. **定义** 设 f 是集合 A 到 B 的关系，如果对每个$x\in A$，都存在唯一$y\in B$，使得$<x，y>\in f$，则称关系 f 为 A 到 B 的函数(Function)，记为$f:A\to B$。当$<x，y>\in f$时，正常记为 y=f(x)，x 称为自变量，y 为 x 在 f 下的函数值。
    1. $dom f=A$，称为函数的定义域
    2. $ran f\subseteq B$，称为函数的值域，$ran f$也可记为 f(A)，为 A 在 f 下的像
    3. $<x,y>\in f\land <x,z>\in f\Leftarrow y=z$
    4. $|f|=|A|$
    5. $f(x)$表示一个变量，f 表示一个集合

# 函数的性质

1. **定义** 设 f 是从集合 A 到 B 的函数：
    1. 对$\forall x_1,x_2\in A$，若$x_1\neq x_2$，有$f(x_1)\neq f(x_2)$，则称 f 为从 A 到 B 的单射(Injection)；
    2. 若$ran f=B$，则称 f 为 A 到 B 的满射(Surjection);
    3. 若 f 既是单射，又是满射，则称 f 为从 A 到 B 的双射(Bijection)或一一映射；
    4. 若$A=B$，则称 f 为 A 上的函数，当 A 上的函数 f 是双射，称 f 为变换(Transform)。
    5. f 是单射的必要条件为$|A|\leq|B|$
    6. f 为满射的必要条件为$|B|\leq|A|$
    7. f 为双射的必要条件为$|A|=|B|$。
2. **定理** 设 A，B 是有限集合，且$|A|=|B|$，f 是 A 到 B 的函数，则 f 是单射当且仅当 f 是满射。

# 函数的复合运算

1. **定义** 设 F，G 是函数，则 FοG 也是函数，且满足：
    1. $dom(F\circ G)=\{x|x\in dom F\land F(x)\in dom G\}$
    2. $\forall x\in dom(F\circ G)，有F\circ G=G(F(x))$
2. **定理** 设$f:A\to B，g:B\to C$
    1. 如果 f，g 满射，则$f\circ g:A→C$满射
    2. 若 f，g 单射，则$f\circ g:A→C$单射
    3. 若 f，g 双射，则$f\circ g:A→C$双射
3. **定理** 设$f:A\to B，g:B\to C$，则$f\circ g:A→C$
    1. 如果$f\circ g:A→C$满射，则 g 满射
    2. 若$f\circ g:A→C$单射，则 f 单射
    3. 若$f\circ g:A→C$双射，则 f 单射，g 满射

# 函数的逆运算

1. **定义** 设$f:A\to B$双射，则$f^{-1}$为 f 的逆函数或反函数(Inverse Function)。
2. **定理** 若$f:A\to B$是双射的，则 f 的逆关系$f^{-1}$是 B 到 A 的双射。
3. **定理** 设$f:A\to B$，双射，则
    $$
    f^{-1}\circ f=I_B \\
    f\circ f^{-1}=I_A \\
    f=f\circ I_B=I_A\circ f
    $$

# 置换

1. **定义** 设 A 是有限集合，$A=\{a_1,a_2,\cdots,a_n\}$，从 A 到 A 的双射函数称为 A 上的置换或排列，记为$P:A\to A$，n 称为置换的阶(Order)。n 阶置换$P:A\to A$常表示为：
    $$
    P=
    \begin{pmatrix}
    a_1&a_2&\cdots&a_n\\
    a'_1&a'_2&\cdots&a'_n
    \end{pmatrix}
    =
    \begin{pmatrix}
    a_1&a_2&\cdots&a_n\\
    P(a_1)&P(a_2)&\cdots&P(a_n)
    \end{pmatrix}
    $$
    其中，$a'_i=P(a_i),i=1,2,\cdots,n$

-   $P(a_1),P(a_2),\cdots,P(a_n)$是$a_1,a_2,\cdots,a_n$的一个排列，排列的总数为$n!$个
-   P 的你函数$P^{-1}$称为逆置换
-   两个置换的复合就是见他们作为函数求复合函数

1. 置换的积：
    - 假设$P:A\to A$为 n 阶置换，$A=\{a_1,a_2,\cdots,a_n\}$，对$a_i\in A$考虑序列$a_i,P(a_i),P^2(a_i),\cdots$，由于$\{a_1,a_2,\cdots,a_n\}$是有限集，则存在最小正整数$r_i$，使得$P^{r_i-1}(a_i)=a_i$，其中$a_i,P(a_i),P^2(a_i),\cdots,P^{r_i-1}(a_i)$互不相同。$(a_i,P(a_i),P^2(a_i),\cdots,P^{r_i-1}(a_i))$称为阶$r_i$的一个循环。
    - 当$r_i<n$时，至少有一个$a_j\in A$，不包含在$(a_i,P(a_i),P^2(a_i),\cdots,P^{r_i-1}(a_i))$中；
    - 对$a_j$重复$a_i$相同的过程，可得$(a_j,P(a_j),P^2(a_j),\cdots,P^{r_j-1}(a_j))$
    - 若$a_j$的循环与$a_i$的循环没有相同的元素时，称它们不相交；
    - 继续这个过程，$A=\{a_1,a_2,\cdots,a_n\}$可以被分成若干子集，这些子集组成不同的循环
        $$
        (a_i,P(a_i),P^2(a_i),\cdots,P^{r_i-1}(a_i)),(a_j,P(a_j),P^2(a_j),\cdots,P^{r_j-1}(a_j)),
        \cdots,\\
        (a_m,P(a_m),P^2(a_m),\cdots,P^{r_m-1}(a_m))
        $$
        把它们写在一起，称为置换的积(Product)。
