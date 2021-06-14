# 二元关系及其表示法

## 序偶与笛卡尔积

1. **定义** 由两个元素 x 和 y 按一定的次序组成的二元组称为有序对或序偶(Ordered)，记作<x,y>，其中 x 是它的第一元素，y 是它的第二元素。
2. **性质**
    1. <x,y>=<y,x>当且仅当 x=y；
    2. <x,y>=<u,v>当且仅当 x=u, y=v;
3. **定义** 设 A，B 是两个集合，称集合$A\times B=\{<x,y>|x\in A\land y\in B\}$为集合 A 与 B 的笛卡尔积(Descartes Product)。
4. **性质**
    1. $|A \times B |=|A|\times|B|(A, B为有限集合);$
    2. $A\times \empty=\empty,\empty\times A=\empty,$
    3. 不适合交换律，即$A\times B \neq B\times A$(除非$A,B=\empty$或 A=B);
    4. 不适合结合律，$(A\times B)\times C \neq A\times (B\times C)$(除非$A=\empty\vee B=\empty \vee C=\empty$)；
    5. 对$\cup$和$\cap$运算满足分配律，
        $$
        \begin{aligned}
        A\times(B\cup C)&=(A\times B)\cup(A\times C)\\
        (B\cup C)\times A&=(B\times A)\cup(C\times A) \\
        A\times(B\cap C)&=(A\times B)\cap(A\times C)\\
        (B\cap C)\times A&=(B\times A)\cap(C\times A) \\
        \end{aligned}
        $$
    6. $A\subseteq C\land B\subseteq D\Leftarrow A\times B\subseteq C\times D$,且当$A=B=\empty$或$A\not=\empty \land B\not=\empty$时，逆命题成立
5. **定义** 一个有序$n(n\geq 2)$元组是一个有序对，它的第一个元素为有序的 n-1 元组$<a_1,a_2,\cdots,a_{n-1}>$ ，第二个元素为$a_n$，记为$<a_1,a_2,\cdots,a_n>$,即：$<<a_1,a_2,\cdots,a_{n-1}>,a_n>=<a_1,a_2,\cdots,a_n>$
    - $<a_1,a_2,\cdots,a_n>=<b_1,b_2,\cdots,b_n>$,当且仅当$a_i=b_i,i=1,2,\cdots,n$
    - n 维空间中的点 M 的坐标$(x_1,x_2,\cdots,x_n)$为有序的 n 元组$<x_1,x_2,\cdots,x_n>$
6. **定义** 设$A_1,A_2,\cdots,A_n$为 n 个集合$(n\geq 2)$，称集合$\{<x_1,x_2,\cdots,x_n>|x_1\in A_1\land x_2\in A_2\land \cdots \land x_n\in A_n\}$为 n 维卡氏积或 n 阶笛卡尔积，记作$A_1\times A_2\times\cdots\times A_n$，当$A_1=A_2=\cdots=A_n$时简记为$A^n$。

## 二元关系

1. **定义** 若集合 F 中的全体元素为有序的 n($n\geq 2$)元组，则称 F 为 n 元关系，特别地，当 n=2 时，称 F 为二元关系，简称关系。
   对于二元关系 F，若$<x,y>\in F$，常记作$xFy$，反之$x\not{F}y$; 规定 $\empty$为空关系，也是二元空关系，简称空关系。
2. **定义** 设 A，B 为两集合，$A\times B$的集合子集 R 称为 A 到 B 的二元关系，特别地，当 A=B 时，称 R 为 A 上的二元关系。
3. 一般来说，若|A|=m，|B|=n，A 到 B 上的二元关系共有$2^{mn}$个，A 上共有$2^{m^2}$个二元关系。
4. 特殊的二元关系：
    1. 空关系
    2. 全域关系：$E_A=\{<x,y>|x\in A\land y\in A\}=A\times A$
    3. 恒等关系：$I_A=\{<x,x>|x\in A\}$
5. **定义** 设 R 为二元关系，则
   $domR=\{x|\exist y(xRy)\}$为 R 的定义域；
   $ranR=\{y|\exist x(xRy)\}$为 R 的值域；
   $fldR=domR\cup ranR$为 R 的域。
   一般地，若 R 是 A 到 B 上的二元关系，则有
    $$
    domR\subseteq A,ranR\subseteq B
    $$

## 关系的表示

1. 集合表示法
   由于关系也是一种特殊的集合，所以可以用集合的两种基本的表示方法(枚举法，描述法)来表示关系；如：设 $A=\{2\}$，$B=\{3\}$，则 A 到 B 上的有关系 $R=\{<2,3>\}$；集合 N 上的“小于等于”关系：$R=\{<x, y>|(x, y) \in N\land(x \leq  y)\}$。
2. 关系图法
   设集合$A=\{x_1,x_2,\cdots,x_n\}$到$B=\{y_1,y_2,\cdots,y_n\}$上的二元关系 R，以集合 A，B 中的元素为顶点，在图中用$\circ$表示顶点，若$x_iRy_j$可自顶点$x_i$向顶点$y_j$引有向边$(x_i,y_j)$，其箭头指向$y_j$，用这种方法画出的图称为关系图(Graph of Relation)。
3. 关系矩阵
   设$R\subseteq A\times B,A=\{a_1,a_2,\cdots,a_m\},B=\{b_1,b_2,\cdots,b_n\}$，那么 R 的关系矩阵$M_R$为一个$m\times n$矩阵，它的第 i，j 分量$r_{ij}$只取 0 或 1，且
    $$
    r_{ij}=
    \begin{cases}
     1,当且仅当a_iRb_j\\
     0,当且仅当a_i\not Rb_j
    \end{cases}
    $$

# 关系的运算

1. **定义** 设 R 和 S 为 A 到 B 的二元关系，其并，交，补，差运算定义如下
    $$
    \begin{aligned}
    R\cup S&=\{<x,y>|xRy\vee xSy\} \\
    R\cup S&=\{<x,y>|xRy\land xSy\} \\
    R - S&=\{<x,y>|xRy\land\neg xSy\} \\
    \overline{R}&=\{<x,y>|\neg xRy\}
    \end{aligned}
    $$
    - 对应的矩阵可以如下方法求取
        $$
        \begin{aligned}
        M_{R\cup S}&=M_R\vee M_S \\
        M_{R\cap S}&=M_R\land M_S \\
        M_{R - S}&=M_{R\land\overline{S}}=M_R\land M_{\overline S} \\
        M_{\overline S}&=\overline{M_S}
        \end{aligned}
        $$
2. **定义** 关系的逆运算:设 R 是 A 到 B 的关系，R 的逆关系或逆是 B 到 A 的关系，记为$R^{-1}$，定义为：$R^{-1}=\{<y,x>|xRy\}$
    - 对$\forall x\in A,y\in B$，有$xRy\Leftrightarrow yR^{-1}x$
    - $M_R$为 R 的关系矩阵，则$M_{R^{-1}}=M'_R$(矩阵转置)
3. **定理** 设 R 和 S 都是 A 到 B 上的二元关系，那么
    1. $(R^{-1})^{-1}=R$
    2. $(\overline R)^{-1}=\overline{R^{-1}}$
    3. $(R\cap S)^{-1}=R^{-1}\cap S^{-1}$
       $(R\cup S)^{-1}=R^{-1}\cup S^{-1}$
       $(R - S)^{-1}=R^{-1} - S^{-1}$
    4. $(R\subseteq S)^{-1}=R^{-1}\subseteq S^{-1}$
    5. $domR^{-1}=ranR,ranR^{-1}=domR$
    6. $\empty^{-1}=\empty,(A\times B)^{-1}=B\times A$
4. **定义** 关系的复合运算：设 R，S 为二元关系，则 R 与 S 的复合关系$R\circ S$定义为：$R\circ S=\{<x,y>|\exist t(xRt\land tSy)\}$，其中$\circ$为复合运算符，$R\circ R$也记为$R^2$.
5. **定理** 设 F，G，H 为任意二元关系，则
    1. $(F\circ G)\circ H=F\circ(G\circ H)$
    2. $(F\circ G)^{-1}=G^{-1}\circ F^{-1}$
    3. $F\circ I_A=I_A\circ F(I_A=\{<x,x>|x\in A\})$
    4. $F\circ \empty=\empty\circ F=\empty$
    5. $F\circ (G\cup H)=(F\circ G)\cup(F\circ H)$
    6. $(G\cup H)\circ F=(G\circ F)\cup(H\circ F)$
    7. $F\circ (G\cap H)=(F\circ G)\cap(F\circ H)$
    8. $(G\cap H)\circ F=(G\circ F)\cap(H\circ F)$
6. **定义** 关系的幂运算：设 R 是集合 A 上的二元关系，则 R 的 n 次幂$R^n$定义为
    1. $R^0=I_A=\{<x,x>|x\in A\}$
    2. $R^{n+1}=R^n\circ R$
7. **定理** 设 R 为 A 上的二元关系，m，n 为自然数，则
    1. $R^{n+1}=R^n\circ R=R\circ R^n=R^m\circ R^{n-m+1}$
    2. $R^m\circ R^n=R^{m+n}$
    3. $(R^m)^n=R^{mn}$
    4. $(R^{-1})^n=(R^n)^{-1}$
8. **定理** 设集合 A 的基数为 n，R 是 A 上的二元关系，那么存在自然数 i，j 使得$R^i=R^j(0\leq i<j\leq 2^{n^2})$
9. **定理** 设 A 是有限集合，且|A|=n，R 是 A 上的二元关系，则
    $$
    \bigcup_{i=1}^{\infty}R^i=\bigcup_{i=1}^n R^i
    $$
10. **定义** 集合在关系下的像：设 R 为二元关系，A 是集合
    1. R 在 A 上的限制$R\Gamma A$定义为$R\Gamma A=\{<x,y>|xRy\land x\in A\}$
    2. A 在 R 下的像 R[A]定义为$R[A]=ran(R\Gamma A)$
11. **定理** 设 F 为关系，A，B 为集合，则
    1. $F\Gamma(A\cup B)=(F\Gamma A)\cup(F\Gamma B)$
    2. $F[(A\cup B)]=F[A]\cup F[B]$
    3. $F\Gamma(A\cap B)=(F\Gamma A)\cap(F\Gamma B)$
    4. $F[(A\cap B)]=F[A]\cap F[B]$

# 关系的性质

1. **定义** 设 R 是 A 上的二元关系，即$R\subset A\times A$，则
    1. 若$\forall x(x\in A\to<x,x>\in R)$，则称 R 是自反的
    2. 若$\forall x(x\in A\to<x,x>\notin R)$，则称 R 是反自反的
    3. 若$\forall x,y(x,y\in A\land xRy\to yRx)$，则称 R 是对称的
    4. 若$\forall x,y(x,y\in A\land xRy\land yRx\to x=y)$，则称 R 是反对称的
    5. 若$\forall x,y,z(x,y,z\in A\land xRy\land yRz\to xRy)$，则称 R 是反对称的
2. 在关系图上
    - 关系 R 是自反的，当且仅当其关系图中，每个节点都有环
    - 关系 R 是反自反的，当且仅当其关系图中的每个节点上都无环
    - 关系 R 是对称的，当且仅当其关系图中，任何一对节点之间，要么有方向相反的两条边，要么无任何边
    - 关系 R 是反对称的，当且仅当其关系图中，任何一对节点之间，至多有一条边
    - 关系 R 是传递的，当且仅当其关系图中，任何三个节点 x, y, z(可相同)之间，若从 x 到 y，y 到 z 均有一条边，则从 x 到 z 一定有一条边存在
3. 在关系矩阵上
    - 关系 R 是自反的，当且仅当其关系矩阵的主对角线上全为 1
    - 关系 R 是反自反的，当且仅当其关系矩阵的主对角线上全为 0
    - 关系 R 是对称的，当且仅当其关系矩阵是对称矩阵
    - 关系 R 是反对称的，当且仅当其关系矩阵为反对称矩阵
    - 关系 R 是传递的，当且仅当其关系矩阵中，对$\forall i,j,k\in[1,n]$，若$r_{ij}=1,r_{jk}=1$，则必有$r_{ik}=1$
4. **定理** 设 R 是集合 A 上的二元关系，则
    1. R 是自反的$\Leftrightarrow I_A\subseteq R$
    2. R 是反自反的$\Leftrightarrow I_A\cap R=\empty$
    3. R 是对称的$\Leftrightarrow R=R^{-1}$
    4. R 是反对称的$\Leftrightarrow R\cap R^{-1}\subseteq I_A$
    5. R 是传递的$\Leftrightarrow R\circ R\subseteq R$
5. **定理** 设 R，S 是 A 上的二元关系，则
    1. R,S 自反$\Leftarrow R^{-1},R\cup S,R\cap S,R\circ S$自反
    2. R,S 反自反$\Leftarrow R^{-1},R\cup S,R\cap S,R-S$反自反
    3. R,S 对称$\Leftarrow R^{-1},R\cup S,R\cap S,R-S$对称
    4. R,S 反对称$\Leftarrow R^{-1},R\cap S,R-S$反对称
    5. R,S 传递$\Leftarrow R^{-1},R\cap S$传递

# 等价关系与划分

1. **定义** 集合的划分：设 A 是一个非空集合，$A_1,A_2,\cdots,A_n$是 A 的任意 n 个非空子集，如果$A_1,A_2,\cdots,A_n$满足： 1. $A_i\cap A_j=\empty,i\neq j,i,j=1,2,\cdots,n$ 2. $\cup_{i=1}^n A_i=A$
   则称集合$\Pi(A)=\{A_1,A_2,\cdots,A_n\}$为集合 A 的一个划分(Partition)，而$A_1,A_2,\cdots,A_n$叫做这个划分的块或类。
2. **定义** 等价关系：设 R 为非空集合 A 上的关系，如果 R 是自反的，对称的，传递的，则称 R 为 A 上的等价关系(Equivalent Relation)。若$<x,y>\in R$，称 x 等价于 y,记作$x\sim y$。
3. **定义** 等价类：设 R 是非空集合 A 上的等价关系，对任意$x\in A$，称集合$[x]_R=\{y|y\in A\land xRy\}$为 x 关于 R 的等价类(Equivalence Class)，其中 x 称为$[x]_R$的生成元，由于$[x]_R$中的任何两个元素 a，b 均相互等价，一般记作$a\sim b$。
4. **定理** 设 R 为非空集合 A 上的等价关系，则
    1. $\forall x\in A,[x]_R\neq \empty$
    2. $\forall x,y \in A,xRy,则[x]_R=[y]_R$
    3. $\forall x,y \in A,x\not Ry,则[x]_R\cap[y]_R=\empty$
    4. $\cup_{x\in A}[x]_R=A$
5. **定义** 设 R 是集合 A 上的等价关系，由 R 确定的一切等价类的集合，称为集合 A 上关于 R 的商集(Quotient Set)，记为$A/R$，即$A/R=\{[x]_R|x\in A\}$
6. **定理** 设 R 是非空集合 A 上的等价关系，则 A 上的关于 R 的商集$A/R$是 A 的一个划分，称之为由 R 导出的等价划分。
7. **定理** 设$\Pi(A)$是非空集合 A 的一个划分，则 A 上的关系$R=\{<x,y>|x,y\in A\land x,y同属于\Pi(A)的一个划分块\}$是 A 上的等价关系，称之为由$\Pi(A)$所导出的等价关系。
    - 若设$\Pi(A)=\{A_1,A_2,\cdots,A_n\}$，则
        $$
        R=(A_1\times A_1)\cup(A_@\times A_2)\cup\dots\cup(A_n\times A_m)=\cup_{i=1}^n A_i^2
        $$

# 次序关系

1. **定义**
    1. 设 R 为非空集合 A 上的关系，如果 R 是**自反的，反对称的，传递的**，则称 R 为 A 上的偏序关系(Partial Order relation)。记作“$\leq$”,读作“小于等于”；
    2. 设 R 为非空集合 A 上的关系，如果 R 是**反自反的，反对称的，传递的**，则称 R 为 A 上的拟序关系(Quasi Order relation)。记作“$<$”；读作“小于”。
    - 偏序关系的逆关系$\leq^{-1}$也是一个偏序，用“$\geq$”表示，读作“大于等于”；拟序关系的逆关系$<^{-1}$也是一个拟序，用“$>$”表示，读作“大于”。
2. **定义** 设$<A, \leq>$是一个偏序集，对$\forall x,y\in A,x\leq y或y\leq x$，则称 x 与 y 是可比的(Comparable),若 x 与 y 是可比的，$x<y$，且不存在$z\in A$，使得$x<z<y$，则称 y 覆盖(Overlay)x。
3. 偏序集的哈斯图(有点类似于图)
    1. 用小圆圈或点表示 A 中的元素，省掉关系图中的所有环(因自反性)；
    2. 对$forall x,y\in A$，若$x<y$则将 x 画在 y 的下方，可省掉关系图中所有边的箭头；
    3. 对$forall x,y\in A$，若 y 覆盖 x，则在 x 与 y 之间连条线，否则无线相连。
4. **定义** 设$<A, \leq>$是一个偏序集，$B\subseteq A,y\in B$
    1. 若$\forall x(x\in B\to y\leq x)$成立，则称 y 为 B 的最小元；
    2. 若$\forall x(x\in B\to y\geq x)$成立，则称 y 为 B 的最大元；
    3. 若$\forall x(x\in B\land x\leq y\to y=x)$成立，则称 y 为 B 的极小元；
    4. 若$\forall x((x\in B\land x\geq y\to y=x)$成立，则称 y 为 B 的极大元。
5. **定义** 设$<A, \leq>$是一个偏序集，$B\subseteq A,y\in A$
    1. 若$\forall x(x\in B\to x\leq y)$成立，称 y 为 B 的上界；
    2. 若$\forall x(x\in B\to x\geq y)$成立，称 y 为 B 的下界；
    3. 令$C=\{y|y为B的上界\}$，则称 C 的最小元为 B 的最小上界/上确界；
    4. 令$D=\{y|y为B的下界\}$，则称 D 的最小元为 B 的最大下界/下确界。

-   上(下)界存在，并不一定存在最小上(下)界；
-   b 是 B 的最大元$\Leftarrow$b 是 B 的极大元，上界，上确界；
-   b 是 B 的最小元$\Leftarrow$b 是 B 的极小元，下界，下确界；
-   a 是 B 的上确界$\land a\in B\Leftarrow$a 是 B 的最大元；
-   a 是 B 的下确界$\land a\in B\Leftarrow$a 是 B 的最小元；
-   若 B 存在上确界，则其上确界唯一；
-   若 B 存在下确界，则其下确界唯一。
6. **定义** 设$<A, \leq>$是一个偏序集，若对$\forall x,y\in A$，x与y都是可比的，则称关系"$\leq$"为全序关系(Total Order Relation)，或线序关系，简称全序或线序，称$<A, \leq>$为全序集/线序集/链。
7. **定义** 设$<A, \leq>$是一个偏序集，若A的任何一个非空子集有最小元，则称"$\leq$"为良序关系(Well Order Relation)，此时$<A, \leq>$称为良序集。