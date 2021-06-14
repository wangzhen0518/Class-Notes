# 命题演算的形式系统

1. 形式系统
    1. 字母表 由不加定义而采用的符号组成，字母表指此形式系统可以使用的符号
    2. 公式集(Form) 字母表上符号串的一个子集，Form 中的元素称为公式，Form 指此形式系统可以使用的符号串
    3. 公理集(Axiom) Form 的一个子集，Axiom 中的元素称为公理， Axiom 指此形式系统一开始便接受而不加证明的定理
    4. 推理规则系(Rule/证明) Rule 中的元素称为推理规则，Rule 规定了公式间的转换关系
    - Axiom 和 Rule 均为空时，系统仅仅为一个语句生成系统
    - 如果 Axiom 非空， 则称为公理系统
    - 若 Axiom 为空， 则称为自然推理系统
2. 语法推论和语义推论的一致性
    1. **可靠性问题** 形式系统中正确推理出来的公式，定理在所讨论的具体实际系统中是否为永真
    2. **完备性问题** 具体实际系统中的永真的语句是否均为形式系统内的定理
3. 命题演算公式集
    1. 字母表
        - 两个运算符：$\neg,\to$
        - 命题变元的可数序列
    2. 公式集(形成规则) 1. 命题变元$x_1,x_2,\cdots,x_n,\cdots$中的每一个都是公式 2. 若 p,q 是公式，则$\neg p,p\to q$是公式 3. 一公式皆由规则 1, 2 的有限次使用形成
       记$X=\{x_1,x_2,\cdots,x_n,\cdots\}$， 则用 L(X)表示由 1-3 形成的所有公式所构成的公式集
4. 命题运算公式的唯一读法
    1. 省括号：中缀表达式$\to$前缀表达式 $p\to q$写成 $\to pq$
    2. 定义权重：
        $$
        w(\neg)=0, w(\to)=-1, w(x_i)=1, i\in N\\
        w(u_1\cdots u_n)=w(u_1)+\cdots+w(u_n)
        w()=0
        $$
    3. 若一字母串是公式，则该串的权重必是 1，而该串的任一真前段的权重都小于 1
    4. 若一字母串是由两个公式并接而成，则并接的方式是唯一的
    5. 确定任一给定字母串是否是公式的算法
        1. 计算权重，权重不为 1 时排除
        2. 权重为 1 时，若该串是单字母串，那只能是$x_i$
        3. 权重为 1 且长度大于 1 时，三种可能：
            1. 该串以$x_i$开头，则肯定不是公式
            2. 该串以$\neg$开头，则去掉$\neg$后对剩下的较短的字母串进行检查，决定于较短字母串是否是公式
            3. 该串以$\to$开头，则去掉权重为-1 的$\to$后，检查剩下较短的字母串(权重为 2)是否是两个公式的并接。若是，则并接方式是唯一的
5. 命题演算公式集的代数结构 
   1. 设有命题变元集$X=\{x_1,x_2,\cdots,x_n,\cdots\}$出发得到的可数的公式集 L(X) 2. 由可数集 X 及二元集{1,2}出发定义列集：

    $$
     \begin{aligned}
     L_0&=X=\{x_1,x_2,\cdots,x_n,\cdots\} \\
     L_1&=(\{1\}\times L_0)\cup(\{2\}\times L_0\times L_0)\\
        &=\{(1,x_1),(1,x_2),\cdots,(1,x_n),\cdots,\\
            (2,x_1,x_1),(2,x_1,x_2),(2,x_2,x_1),\cdots\}
    L_2&=(\{1\}\times L_1)\cup(\{2\}\times L_0\times L_1)\cup(\{2\}\times L_1\times L_0)\\
    L_3&=
     \end{aligned}
    $$

    > 1
    > 2
    > 3
    > 4
    > 5

6. 命题演算 L
    1. **定义** 命题变元集$X=\{x_1,x_2,\cdots,x_n,\cdots\}$上的命题演算 L 是指带有下面规定的公理和证明的命题代数 L(X)：
        1. **公理** 取 L(X)具有以下形式的公式作为公理
            1. $p\to (q\to p)$
            2. $(p\to(q\to r))\to((p\to q)\to(p\to r))$
            3. $(\neg p\to \neg q)\to (q\to p)$
        2. **证明** 设$\Gamma \subseteq L(X),p\in L(X)$,若存在 L(X)的公式有限序列$p_1,\cdots,p_n,$其中$p_n=p$,且每个$p_k(k=1,…,n)$满足 1. $p_k\in \Gamma$ 2. $p_k$是公理 3. 存在$i,j < k$使$p_j=p_i\to p_k$
           则称公式 p 是从公式集$\Gamma$可证的，$p_1,\cdots,p_n$叫做 p 从$\Gamma$的证明
    2. **语法推论** 建立命题演算 L 后，进一步规定：
        1. 如果公式 p 从公式集$\Gamma$可证， 则记作$\Gamma\vdash p$或$\Gamma\vdash_L p$。这时$\Gamma$中的公式叫做假定， p 叫做假定集$\Gamma$的语法推论。
        2. 若$\empty\vdash p$，则称 p 是 L 的定理，记作$\vdash p$。p 在 L 中从$\empty$的证明$p_1,\cdots,p_n$简称为 p 在 L 中的证明。
        3. 在一个证明中，当$p_j=p_i\to p_k(i,j<k)$时，就说$p_k$由$p_i,p_i\to p_k$使用假言推理(Modus Ponens)这条推理规则而得，即使用 MP 而得
    3. **结论**
        1. 若 p 是 L 的公理，则$\Gamma\vdash p$对任一公式集$\Gamma$都成立
        2. 若$\vdash p$，即 p 是 L 的定理， 则$\Gamma\vdash p$对任一公式集$\Gamma$都成立
        3. 若$p\in \Gamma$，$\Gamma\vdash p$
        4. $\{p,p\to q\}\vdash q$
        5. 若$\Gamma\vdash p_n$，且已知$p_1,\cdots,p_n$是$p_n$从$\Gamma$的证明，则当$1\leq k\leq n$时，有$\Gamma\vdash p_k$，且$p_1,\cdots,p_k$是$p_k$从$\Gamma$的证明
        6. 若$\Gamma$是无限集，且$\Gamma\vdash p$，则存在$\Gamma$的有限子集$\Delta$使$\Delta\vdash p$
    4. **无矛盾公式集**
       如果对任何公式 q，$\Gamma\vdash q$和$\Gamma\vdash\neg q$二者都不同时成立，就称公式集$\Gamma$是无矛盾公式集，否则称$\Gamma$为有矛盾公式集。
    5. 若$\Gamma$是有矛盾公式集， 则对 L 的任一公式 p，都有$\Gamma\vdash q$。
7. 演绎定理
$$
\Gamma\cup\{p\}\vdash q\Leftrightarrow \Gamma\vdash p\to q
$$






