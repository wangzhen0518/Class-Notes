# 命题与命题联结词

1. 定义 1
   具有**确切真值**的**陈述句**称为命题。
2. 命题类型：
    - 简单命题
    - 复合命题
3. 命题联结词
    1. 非：$\neg$
    2. 析取词：$\vee$
    3. 合取词：$\wedge$
    4. 蕴含词：$\to$
    5. 等价词：$\longleftrightarrow$
4. 命题公式：

    - 一个特定的命题是一个**常值命题(Constant Proposition)**，它不是具有值“T”(“1”)，就是具有值“F”(“0”)。而一个任意的没有赋予具体内容的原子命题是一个变量命题，常称它为**命题变量(或命题变元、命题变项)(Proposition Variable)**。命题变量无具体的真值，它的值域是集合{T，F}(或{1，0})。
    -   1. 命题变元本身是一个公式；
        2. 如果 P 是公式，则$\neg P$也是公式；
        3. 如果 P，Q 是公式，则$P\wedge Q﹑ P\vee Q﹑ P\to Q﹑ P\leftrightarrow Q$也是公式；
        4. 命题公式(Prepositional Formula)是仅由有限步使用规则(1)~(3)后产生的结果。公式常用符号$G\wedge H$…等表示。

    - 合取公式的层次：

    1. 若公式 A 是一单个的命题变项，则称 A 为 0 层公式；
    2. 称 A 是 n+1(n≥0)层公式只需满足下列情况只一：
        1. $A=\neg B$，B 是 n 层公式；
        2. $A=B\wedge C$，其中 B，C 分别为 i 层和 j 层公式,且 n=max(i, j)；
        3. $A=B\vee C$，其中 B，C 的层次同 b；
        4. $A=B\to C$，其中 B，C 的层次同 b；
        5. $A=B\leftrightarrow C$，其中 B，C 的层次同 b.

# 公式的解释与真值表

1. **定义** 设命题变元$P_1, P_2, …,P_n$是出现在公式 G 中的所有命题变元，指定$P_1, P_2, …,P_n$一组真值，则这组这组称为 G 的一个**解释(Explanation)**,并记作 I。
2. **定义** 公式 G 在其所有可能的解释下所取真值的表，称作 G 的**真值表(Truth)**。
3. 重言式
    1. 公式 G 称为永真公式（重言式），如果在它的所有解释下都为“真”；
    2. 公式 G 称为可满足的，如果它不是永假的；
    3. 公式 G 称为永假公式（矛盾式）, 如果在它的所有解释下都为“假”;有时也称永假公式为不可满足公式。
4. 恒等式

    - 公式 G，H，如果在其任意解释下，其真值相同，则称 G 是 H 的等价式(Equivalent)或称 G 恒等于 H，记作$G\Leftrightarrow H$。
    - **定理** 对于公式 G 和 H, $G\Leftrightarrow H$的充分必要条件是公式$G\leftrightarrow H$是重言式。
    - 常用逻辑恒等式
      | 逻辑恒等式 | 含义 |
      | ------------------------------------------------------------ | -------------------------- |
      | $\neg \neg P\Leftrightarrow P$ | 双否定 |
      | $P\vee P\Leftrightarrow P$ | $\vee$的幂等律 |
      | $P\wedge P\Leftrightarrow P$ | $\wedge$的幂等律 |
      | $P\vee Q \Leftrightarrow Q \vee P$ | $\vee$的交换律|
      | $P \wedge Q \Leftrightarrow Q \wedge P$ | $\wedge$的交换律 |
      | $(P\vee Q) \vee R  \Leftrightarrow P \vee (Q \vee R)$ | $\vee$的结合律 |
      | $(P\wedge Q) \wedge R  \Leftrightarrow P \wedge (Q \wedge R)$ | $\wedge$的结合律 |
      | $P\wedge (Q \vee R)  \Leftrightarrow (P \wedge Q)\vee(P\wedge R)$| $\wedge$在$\vee$上的结合律|
      | $P\vee (Q \wedge R)  \Leftrightarrow (P \vee Q)\wedge(P\vee R)$ | $\vee$在$\wedge$上的结合律 |
      | $\neg(P \vee Q) \Leftrightarrow \neg P \wedge \neg Q$| 德·摩根定律|
      | $\neg(P \wedge Q) \Leftrightarrow \neg P \vee \neg Q$ | 德·摩根定律|
      | $P \vee(P \wedge Q) \Leftrightarrow P$ | 吸收律|
      | $P \wedge(P \vee Q) \Leftrightarrow P$ | 吸收律 |
      | $P\leftrightarrow Q \Leftrightarrow (P \wedge Q)\vee(\neg P \wedge\neg Q)$| 等价等值式|
      | $P\vee T \Leftrightarrow T$ | 零律 |
      | $P\wedge F \Leftrightarrow F$ | 零律 |
      | $P\wedge T \Leftrightarrow P$ | 同一律 |
      | $P\vee F \Leftrightarrow P$ | 同一律 |
      | $P\vee \neg P \Leftrightarrow T$ | 排中律 |
      | $P\wedge \neg P \Leftrightarrow F$ | 矛盾律 |
      | $(P\wedge Q) \to R) \Leftrightarrow P \to (Q\to R)$ | 输出律 |
      | $(P\to Q)\wedge(P\to \neg Q) \Leftrightarrow \neg P$ | 归谬律 |
      | $P\to Q \Leftrightarrow \neg Q \to \neg P$ | 逆反律 |

5. 永真蕴含式

    - **定义** 若$A\to B$是一永真式，那么称为永真蕴含式，记为$A\Rightarrow B$，读作 A 永真蕴含 B.
    - | 常用的永真蕴含式                                                               |
      | ------------------------------------------------------------------------------ |
      | $P \Rightarrow P \vee Q$                                                       |
      | $P \wedge Q \Rightarrow P$                                                     |
      | $P\wedge(P\to Q) \Rightarrow Q $                                               |
      | $(P\to Q)\wedge \neg Q \Rightarrow \neg P$                                     |
      | $\neg P \wedge(P\vee Q)\Rightarrow Q$                                          |
      | $(P\to Q)\wedge(Q\to R)\Rightarrow P\to R$                                     |
      | $P\to Q \Rightarrow((Q\to R)\to(P\to R))$                                      |
      | $(P\leftrightarrow Q)\wedge(R\leftrightarrow Q)\Rightarrow P\leftrightarrow R$ |

6. 恒等式和永真蕴含式的两个性质
    1. $若A\Leftrightarrow B，B\Leftrightarrow C，则A\Leftrightarrow C；若A\Rightarrow B，B\Rightarrow C，则A\Rightarrow C。$
    2. $若A\Rightarrow B，B\Rightarrow C，则A\Rightarrow B\wedge C。$
7. 代入规则和替换规则
    1. **代入定理** 设$G(P_1, …,P_n)$是一个命题公式，其中$P_1, …,P_n$是命题变元，$G_1(P_1, …,P_n), … G_n(P_1, …,P_n)$为任意的命题公式，此时若 G 是永真公式或永假公式，则用$G_1取代P_1,…,G_n取代P_n后$，得到的新的命题公式$G(G_1,…,G_n)\Leftrightarrow G'(P_1, …,P_n)$也是一个永真公式或永假公式。
    2. **替换定理** 设$G_1$是 G 的子公式，$H_1$是任意的命题公式，在 G 中凡出现$G_1$处都以$H_1$替换后得到的新的命题公式 H，若$G_1\Leftrightarrow H_1$，则$G\Leftrightarrow H$。
8. 对偶原理
    1. **定义** 设公式 A，其中仅有联结词$\wedge，\vee，\neg$。在 A 中将$\wedge，\vee$，T，F 分别换以$\vee，\wedge$，F，T 得到公式 A'，则 A'称为 A 的对偶公式。对 A'采取同样的替换，又得到 A，所以 A 也是 A'的对偶，即对偶是相互的。
    2. **定理** 设 A 和 A'是对偶式，$P_1,P_2, …,P_n$是出现于 A 和 A'中所有命题变元，于是$\neg A(P_1,P_2, …,P_n)<=>A'(\neg P_1, \neg P_2, …, \neg P_n)$。
    3. **定理(对偶原理)** 若$A\Leftrightarrow B$，且 A，B 为命题变元$P_1,P_2, …,P_n$及联结词$\wedge，\vee，\neg$构成的公式，则$A'\Leftrightarrow B'$。
    4. **定理** 如果$A\Rightarrow B$，且 A，B 为命题变元$P_1,P_2, …,P_n$及联结词$\wedge，\vee，\neg$构成的公式，则$B'\Rightarrow A'$。

# 联结词的完备集

1. 联结词的扩充
   在之前的基础上，增加$\bar{\vee}(异或)，\nrightarrow(蕴含否定)，\uparrow(与非)，\downarrow(或非)$。
   $P\bar\vee Q\Leftrightarrow \neg(P\leftrightarrow Q)$，$P\nrightarrow Q\Leftrightarrow \neg(P\to Q)$，$P\uparrow Q\Leftrightarrow \neg(P\land Q)$，$P\downarrow Q\Leftrightarrow \neg(P\vee Q)$。
2. 全功能联结词
    - 若 S 有以下性质，则称 S 为极小联结词完备集。
        1. 用 S 中的联结词表示的公式设 S 是联结词，可以等价地表示任何命题公式，则称 S 是一个联结词完备集 (或全功能集合) (Adequate Set of Connectives)
        2. S 是一个联结词的完备集，且 S 中无冗余的联结词(即集合中不存在可以被其中的其它联结词所定义的联结词)

# 范式

1. **定义**
    1. 命题变元或命题变元的否定称为文字；
    2. 有限个文字的析取式称为简单析取式(基本和)，有限个文字的合取式称为简单合取式(基本积)；
    3. 由有限个简单合取式构成的析取式称为析取范式(Disjunctive Normal From)，由有限个简单析取式构成的合取式称为合取范式(Conjunctive Normal From)。
2. **性质**
    1. 一个文字既是一个析取范式又是一个合取范式；
    2. 一个析取范式为矛盾式，当且仅当它的每个简单合取式是矛盾式；
    3. 一个合取范式为重言式，当且仅当它的每个简单析取式是重言式。
3. 主析取范式&主合取范式
    - **定义**
        1. 包含 A 中所有命题变元或其否定一次仅一次的简单合取式，称为极小项；
        2. 包含 A 中所有命题变元或其否定一次仅一次的简单析取式，称为极大项；
        3. 由有限个极小项组成的析取范式称为主析取范式；
        4. 由有限个极大项组成的合取范式称为主合取范式。
    - **性质**
        1. 没有两个不同的极小项是等价的，且每个极小项只有一组真值指派，使该极小项的真值为真。
        2. 没有两个不同的极大项是等价的，且每个极大项只有一组真值指派，使该极大项的真值为假。
        3. 任意两极小项的合取必假，任意两个极大项的析取必为真。极大项的否定是极小项，极小项的否定是极大项，即
            $$
            M_i\vee M_j\Leftrightarrow T\\
            m_i\land m_j\Leftrightarrow F\\
            m_i\Leftrightarrow \neg M_i\\
            M_i\Leftrightarrow \neg m_i
            $$
        4. 所有极小项的析取为永真公式，所有极大项的合取是永假公式，即
            $$
            \bigvee_{i=0}^{2^n-1}m_i=T\\
            \bigwedge_{i=0}^{2^n-1}M_i=F
            $$
    - **定理** 任何命题公式的主析取范式和主合取范式存在且唯一，即任何命题公式都有且仅有一个与之等价的主合取范式和主析取范式。
    - **构造方式**
        1. 选出公式的真值结果为**真**的所有行，在这样的行中，找到其每一个解释所对应的**极小项**，将这些极小项**析取**即可得到相应的**主析取范式**
        2. 选出公式的真值结果为**假**的所有行，在这样的行中，找到其每一个解释所对应的**极大项**，将这些极大项**合取**即可得到相应的**主合取范式**
    - **唯一性**
    - **主合取范式&主析取范式转换**
      找互补项，进行替换即可

# 命题逻辑的推理理论

-   **定义** 设$G_1，G_2，…，G_n$，H 是命题公式，若对于$G_1，G_2，…，G_n$，H 中出现的命题变元的任意一组赋值，或者$G_1\land G_2\land …G_n$为假，或者当$G_1\land G_2\land …G_n$为真，H 也为真，则称 H 是$G1，G_2，…，G_n$的有效结论(Efficacious Conclusion)或逻辑结果(Logic Conclusion)。 $G_1，G_2，…，G_n$仍为一组前提(Premise)。
-   **定理** 命题公式$G_1，G_2，…，G_n$推出结论 H 的推理正确或公式 H 是前提条件${G_1，G_2，…，G_n}$的逻辑结果，当且仅当$(G_1\land G_2\land …G_n)\to H$为重言式。
-   证明结论有效的方法
-   1. 真值表
-   2. 等值演算
-   3. 主析取范式
-   4. 构造证明法
       构造证明法是依据一些公认的推理规则，从前提出发，推导结论，它可以看作公式的序列，其中每个公式都是按照事先规定的规则得到的，且可将所用的规则在公式后写明，该系列最后一个公式是所要证明的结论。
       |推理定理| |
       |---|---|
       |$A\Rightarrow A\vee B$|附加律|
       |$A\land B\Rightarrow A$|化简律|
       |$(A\to B) \land A \Rightarrow B$| 假言真理|
       |$(A\to B) \land\neg B \Rightarrow \neg A$| 拒取式|
       |$(A\vee B) \land \neg B \Rightarrow A$|析取三段论|
       |$(A\to B) \land (B\to C)\Rightarrow A\to C$| 假言三段论|
       |$(A\leftrightarrow B) \land (B\leftrightarrow C)\Rightarrow A\leftrightarrow C$|等价三段论|
       |$(A\to B)\land(C\to D)\land(A\vee C)\Rightarrow(B\vee D)$| 构造性二难|
       |$(A\to B)\land(\neg A\to B)\land(A\vee \neg A) \Rightarrow B$| 构造性二难(特殊形式)|
       |$(A\to B)\land (C\to D)\land(\neg B\vee \neg D) \Rightarrow(\neg A\vee\neg C)$|破坏性二难|
        - 附加前提证明法(CP 规则)
          若$P_1，P_2，…，P_n$，$P\models Q$，则$P_1，P_2，…，P_n \models P\to Q$。
        - 反证法
            - **定义**
              设$G_1，G_2，…，G_n$是一组命题公式$P_1，P_2，…，P_n$是出现在$G_1，G_2，…，G_n$中的一切命题变元，I 是它的任意解释，若有解释 I 使 $G_1\land G_2\land …\land G_n$取值为“真”，则称公式$G_1，G_2，…， G_n$是一致的(Consistency)。如对任意的解释 I，都有$G_1\land G_2\land …\land G_n$取值为“假”，则称公式$G_1，G_2，…，G_n$是不一致的(Inconsistency),或者说$G_1\land G_2\land …\land G_n$是一个矛盾式。
            - **定理**
              设命题公式集合${G_1，G_2，…，G_n}$是一致的，于是从前提集合${G_1，G_2，…，G_n}$出发可以逻辑地推出公式 H 的充要条件是从前提集合${G_1，G_2，…，G_n，\neg H}$出发，可以逻辑推出一个矛盾式来。
