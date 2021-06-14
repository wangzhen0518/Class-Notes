# 弦振动方程建模

## 一些近似

1. 弦可任意形变，张力沿切线方向
2. 弦只在平面内运动
3. 竖直运动振幅为考察物理量，记为$u=u(t,x)$，微小振动
4. 外力也在竖直方向，分布密度$g(t,x)$
5. 线密度为$\rho(x)$

## 受力分析

任取$(x, x+\delta x)$微元分析
张力$\vec{ T }=(T_1,T_2)$，张力沿切线方向:$\frac{T_2}{T_1}=u_x'$
外力$\vec{F}=\int_{x}^{x+\delta x}g(t,s)dx$

-   水平方向
    由于微元水平方向无运动，故水平方向合力为 0，即$T_1(x) = T_1(x+\delta x)$，所以 T_1 与 x 无关

-   竖直方向

    $$
    T_2(x+\delta x)-T_2(x)+\int_{x}^{x+\delta x}g(t,x)dx=\int_{x}^{x+\delta x}\rho(t,x)u_{tt}(t,x)dx
    $$

    令

    $$
    \delta x\rightarrow 0
    $$

    得到

    $$
    T_2'(t,x)+g(t,x)=\rho(t,x)u_{tt}(t,x)
    $$

-   综上，代入$$T_2=T_1\cdot u_x'$$
    得到$$T_1(t)u_{xx}+g(t,x)=\rho(t,x)u\_{tt}(t,x)$$
    由于$\lvert u_x'\rvert\ll1$，故 T 的模

$$
T=\sqrt{T_1^2+T_2^2}=T_1\sqrt{1+u_x'^2}\approx T_1(t)
$$

且微元弦长$$\Delta s=\int_x^{x+\delta x}\sqrt{1+u_x'^2},dx\approx\Delta x$$即，可认为微元长度没有变化
最终方程为

$$
\rho(x) \frac{ \partial^2 u}{\partial t^2}=T \frac{ \partial^2u}{\partial x^2}+g(t,x)
$$

再假设弦是均匀的，即$\rho$是常数
​ 式子可写为

$$
\frac{\partial^2u}{\partial t^2}=a^2\frac{\partial^2u}{\partial x^2}+f(t,x)\\
    (a=\sqrt{\frac{T}{\rho}},f=\frac{g}{\rho})
$$

> **高维振动**
> 标准形式$$u_{tt}=a^2\Delta_2u+f(t,x,y)$$

---

# 热传导方程建模

## 热平衡分析

1. 流入热量

-   沿 x 轴流入热量

    -   左侧面

        $$
        dQ_1=-k\frac{\partial u}{\partial \vec{n}}(x)dsdt=-k\frac{\partial u}{\partial x}(x)dydzdt\quad(\vec{n}沿x轴方向)
        $$

    -   右侧面

        $$
              dQ_2=-k\frac{\partial u}{\partial \vec{n}}(x+\Delta x)dsdt=-k\frac{\partial u}{\partial x}(x+\Delta x)dydzdt\quad(\vec{n}沿-x轴方向)
        $$

    -   总热量
        $$
        dQ_x=dQ_1-dQ_2\\
        \qquad\qquad\qquad\qquad\qquad\qquad=k(\frac{\partial u}{\partial x}(x+\Delta x)-\frac{\partial u}{\partial x}(x))dydzdt\\
        \qquad\qquad=ku_{xx}dxdydzdt\\
        \qquad=ku_{xx}dVdt
        $$

-   沿 y，z 轴流入热量
    与 x 轴同理，
    $$
    dQ_y=ku_{yy}dVdt\\
    dQ_z=ku_{zz}dVdt
    $$
    所以
    $$
    dQ_1=dQ_x+dQ_y+dQ_z=k\Delta udVdt
    $$

2. 外界流入热量
   $$d Q_2=f(t,x,y,z)dVdt$$

3. 物体升温所需热量
   $$dQ_3=c\rho dV[u(t+\Delta t,x,y,z)-u(t,x,y,z)]=c\rho u_t'dVdt$$

4. 热平衡方程

    $$
    dQ_1+dQ_2=dQ_3\\
    k\Delta udVdt+f(t,x,y,z)dVdt=c\rho u_t'dVdt
    $$

    令

    $$
    dV,dt\rightarrow0
    $$

    得

$$
k\Delta u+f(t,x,y,z)=c\rho u_t'
$$

令

$$
a=\sqrt{\frac{k}{c\rho}}
$$

则方程化为

$$
\frac{\partial u}{\partial t}=a^2\Delta u+\frac{1}{c\rho}f(t,x,y,z)
$$

如果是稳定温度场，且无热源，那么$u_t'=0$，得到

$$
\Delta u=0
$$

如果有热源，得到泊松方程

$$
\Delta u=g(x,y,z)
$$

这里

$$
g(x,y,z)=-\frac{1}{k}f(x,y,z)
$$

# 热传导方程初边值问题

-   $(\alpha\frac{\partial u}{\partial t}+\beta u)|_s=\phi(x,y,z)$

1. $\alpha=0$：第一类边界条件(迪利克雷条件)
2. $\beta=0$：第二类边界条件(诺伊曼条件)
3. $\alpha、\beta$都不为 0：第三类边界条件(诺平条件)

> 符合上述边界条件的定解问题分别称为第一、二、三边值问题。

## 第一类边界条件

已知 S 上的物体温度

$$
u|_S=\mu(t,x,y,z)((x,y,z)\in S,t>0)
$$

## 第二类边界条件

已知 S 上向外流出的热量的热流密度 q(t,x,y,z)，由热传导定律，得

$$
\frac{\partial u}{\partial \vec{n}}|_S=-\frac{q(t,x,y,z)}{k}((x,y,z)\in S,t>0)
$$

这里，$\vec{n}$是边界面 S 的外法向。特别地，当$q\equiv 0$时，物体表面 S 是绝热的。

## 第三类边界条件

物体的边界面处，物体和外部介质有热交换，热交换遵循牛顿定律：从物体流向外部介质的热流密度 q 跟物体与介质在表面处的温度差成正比，边界条件变为：

$$
(k\frac{\partial u}{\partial t}+hu)|_S=h\theta
$$

> 如果以上三类边界条件的右端恒等于零，则称为齐次边界条件；否则，称为非齐次边界条件。

# 定解问题适定性

1. 解需要唯一存在；
2. 方程系数或约束条件微小变化下，解的变化也微小。

# 线性方程求解基本原理

## 叠加原理

-   不同作用(线性)叠加产生的效果$\Leftrightarrow$不同作用产生效果的(线性)叠加

1. 记二阶线性微分算子

    $$
    L=\sum_{i,j=1}^{n}a_{ij}\frac{\partial^2}{\partial x_i\partial x_j}+2\sum_{i=1}^{n}b_i\frac{\partial}{\partial x_i}+c
    $$

    则一般形式的二阶常系数线性微分方程可写为

    $$
    Lu=f
    $$

    最一般的线性边界条件

    $$
    (\alpha u+\beta \frac{\partial u}{\partial t})|_s=\phi(x,y,z)
    $$

    可写为

    $$
    Lu|_S=(\alpha+\beta \frac{\partial}{\partial\vec{n}})u|_S=\phi
    $$

2. **叠加原理 1**
   设$u_i$满足线性方程
    $$
    Lu_i=f_i,
    $$
    则有
    $$
    L\sum_{i=1}^{n}c_i u_i=\sum_{i=1}^{n}c_i f_i
    $$
3. **叠加原理 2**
   设$u_i$满足线性方程
    $$
    Lu_i=f_i,
    $$
    且级数$u=\sum_{i=1}^{+\infty}c_i u_i$收敛，则有
    $$
    Lu=L\sum_{i=1}^{+\infty}c_i u_i=\sum_{i=1}^{+\infty}c_i f_i
    $$
4. **叠加原理 3**
   设$u(M,M_0)$满足线性方程
    $$
    Lu=f(M,M_0),
    $$
    其中 M 表示自变量组，$M_0$表示参数组。
    又设积分
    $$
    U(M)=\int_V u(M,M_0)dM_0
    $$
    收敛，
    则有
    $$
    LU(M)=L\int_V u(M,M_0)dM_0=\int_V Lu(M,M_0)dM_0=\int_V f(M,M_0)dM_0
    $$

## 齐次化原理

1.  **齐次化原理 1**
    设$\omega(t,M;\tau)$满足齐次方程的柯西问题(这里，M 是自变量组(x,y,z)，$\tau$为参数)

    $$
    \begin{cases}
    \frac{\partial^2 \omega}{\partial t^2}=L\omega\quad(M\in R^3,t>\tau),\\
    \\
    \omega|_{t=\tau}=0,\\
    \\
    \frac{\partial\omega}{\partial t}|_{t=\tau}=(\tau,M),
    \end{cases}
    $$

    则非齐次方程的柯西问题

    $$
    \begin{cases}
    \frac{\partial^2 u}{\partial t^2}=Lu+f(t,M)\quad(M\in R^3,t>\tau),\\
    \\
    u|_{t=0}=0,\\
    \\
    \frac{\partial u}{\partial t}|_{t=0}=0,
    \end{cases}
    $$

    的解为

    $$
    u=\int_0^t \omega(t,M;\tau)d\tau
    $$

2.  **齐次化原理 2**
    设$\omega(t,M;\tau)$满足齐次方程的柯西问题(这里，M 是自变量组(x,y,z)，$\tau$为参数)
    $$
    \begin{cases}
    \frac{\partial \omega}{\partial t}=L\omega\quad(M\in R^3,t>\tau),\\
    \\
    \omega|_{t=\tau}=0,
    \end{cases}
    $$
    则非齐次方程的柯西问题
    $$
    \begin{cases}
    \frac{\partial u}{\partial t}=Lu+f(t,M)\quad(M\in R^3,t>\tau),\\
    \\
    u|_{t=0}=0,
    \end{cases}
    $$
    的解为
    $$
    u=\int_0^t \omega(t,M;\tau)d\tau
    $$
