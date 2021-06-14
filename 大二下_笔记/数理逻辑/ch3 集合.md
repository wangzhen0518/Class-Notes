# 集合的基本概念

1. 集合的**定义** 任何被称为“成员”或“元素”的对象的聚集称为集合(Set)
2. 集合的表示
	1. 枚举法
	2. 描述法
	3. 文氏图法
3. 集合与元素的关系
   属于/不属于，即$\in/\notin$
4. 集合特性
    1. 确定性
    2. 互异性
    3. 无序性
5. 集合之间的关系
    1. 相等
       如果$A\subseteq B$且$B\subseteq A$，则称集合 A、B 相等，记为 A=B。
    2. 包含
       设 A，B 为集合，如果$B\subseteq A$且$B≠A$，则称 B 是 A 的真子集(Proper Subset)，记作$B\subseteqq A$，称$\subseteqq $为真包含关系(Properly Inclusion Relation)，如果 B 不是 A 的真子集，则记作$B\nsubseteq A$
    3. **定义** 含有 n 个元素的集合 A 称为**n 元集**，它的 m 个元素($m\leq n$)的子集称为 A 的 m 元子集。
    4. 幂集：把集合 A 的全体子集构成的集合称为 A 的幂集，记为 P(A)或$2^A$，符号化为：$P(A)=\{x|x\subseteq A\}$

# 集合的运算

1. 并
   设 A，B 是两个集合，则 A 与 B 的并集(Union)定义为：$A\cup B=\{x|x\in A \vee x \in B\}$，$\cup$称为并运算(Union Operation)。
2. 交
   设 A，B 是两个集合，则 A 与 B 的交集(Intersection)定义为：$A\cap B=\{x|x\in A \land x \in B\}$，$\cap$称为交运算(Intersection Operation)。
3. 差
   设 A，B 是两个集合，则 A 与 B 的差集(Subtraction)定义为：$A- B=\{x|x\in A \land x \notin B\}$；- 称为差运算(Subtraction Operation)，A-B 也可叫做相对补集。
4. 补
   设 U 为全集，A 是 U 的子集，则集合 A 的补集(Complement)定义为：$\bar{A}=U-A=\{x|x\in U \land x \notin A\}$，也可记为$\sim A$，$\bar{   }$，$\sim$称为补运算(Complement Operation)。
5. 对称差
   设 A，B 是两个集合，则 A 与 B 的对称差集(Symmetric Differences)定义为：$A\oplus B=(A-B)\cup (B-A)$；$\oplus$称为对称差运算(Symmetric Differences Operation)。

# 有限集合的计数

1. 鸽笼原理
    - 若有 n+1 个鸽子住进 n 个鸽笼，则至少有一个鸽笼至少住进 2 只鸽子。
    - (鸽笼原理的推广)若有 n 只鸽子住进 m 个鸽笼，则至少有一个鸽笼至少住进$\lfloor\frac{n-1}{m}\rfloor+1$只鸽子。
2. 容斥原理
    - 设 A 和 B 是任意有限集合，则$|A\cup B|=|A|+|B|-|A\cap B|$
    - 设 U 为全集，A 和 B 是任意有限集合，则$|\bar{A}\cap\bar{B}|=|U|-(|A|+|B|)+|A\cap B|$
    - 设$A_1,A_2,\dots,A_n$是任意有限集合，则
        $$
        |A_1\cup A_2\cup \dots \cup A_n|=\sum_{1\leq i\leq n}|A_i|-\sum_{1\le i<j\le n}|A_i\cap A_j|+\sum_{1\le i<j<k\le n}|A_i\cap A_j\cap A_k|-\dots+(-1)^{n-1}|A_1\cap A_2\cap \dots \cap A_n|
        $$
    - 设 U 为全集，$A_1,A_2,\dots,A_n$是任意有限集合，则
        $$
        |\bar{A_1}\cup \bar{A_2}\cup \dots \cup \bar{A_n}|=|U|-\sum_{1\leq i\leq n}|A_i|+\sum_{1\le i<j\le n}|A_i\cap A_j|-\sum_{1\le i<j<k\le n}|A_i\cap A_j\cap A_k|+\dots+(-1)^{n}|A_1\cap A_2\cap \dots \cap A_n|
        $$
