# 弦振动方程求解

$$
\begin{cases}
u_{tt}=a^2u_{xx} \quad(0<x<l,t>0)\\
u(t,0)=u(t,l)=0 \quad(边界条件)\\
u(0,x)=\varphi(x),u_t(0,x)=\psi(x)\quad(初始条件)
\end{cases}
$$

设

$$
u(t,x)=X(x)T(t)
$$

带入方程得

$$
T''(t)X(x)=a^2T(t)X''(x)
$$

两边同除$T(t)X(x)$

$$
\frac{T''(t)}{a^2T(t)}=\frac{X''(x)}{X(x)}=-\lambda\quad(\lambda为一常数)
$$

-   先解

    $$
    X''(x)=-\lambda X(x)
    $$

    1. 若$\lambda<0$，解得
        $$
        X(x)=A_1e^{\sqrt{-\lambda}x}+A_2e^{-\sqrt{-\lambda}x}
        $$
        将$X(0)=X(l)$带入得
        $$
        \begin{aligned}
         A_1+A_2&=0\\
        A_1e^{2\sqrt{-\lambda}l}+A_2&=0
        \end{aligned}
        $$
        得
        $$
        \lambda=0,不符
        $$
    2. 若$\lambda=0$，解得
        $$
        X(x)=C_1x+C_2
        $$
        将$X(0)=X(l)$带入得
        $$
        C_1=C_2=0
        $$
        即
        $$
        X=0,不符
        $$
    3. 若$\lambda>0$，解得
        $$
         X(x)=A_1e^{i\sqrt{\lambda}x}+A_2e^{-i\sqrt{\lambda}x}
        $$
        将$X(0)=X(l)$带入得
        $$
        \begin{aligned}
        A_1+A_2&=0\\
        A_1e^{2i\sqrt{\lambda}l}+A_2&=0
        \end{aligned}
        $$
        从而有
        $$
        \begin{aligned}
         e^{2i\sqrt{\lambda}l}&=1\\
        2\sqrt{\lambda}l&=2k\pi\\
        \lambda&=(\frac{k\pi}{l})^2 \quad(k\in N^+)
        \end{aligned}
        $$
        又有
        $$
        A_1=-A_2
        $$
        所以
        $$
        \begin{aligned}
        X&=A_1e^{i\frac{k\pi}{l}x}+A_2e^{-i\frac{k\pi}{l}x}\\
        &=Asin(\frac{k\pi}{l}x)
        \end{aligned}
        $$
        即
        $$
        X_n=Asin(\frac{n\pi x}{l})
        $$

-   再解$T''(t)=-\lambda a^2T(t)$，即$T''(t)=-(\frac{n\pi a}{l})^2T(t)$，得
    $$
    T_n(t)=C_ncos(\frac{n\pi a}{l}t)+D_nsin(\frac{n\pi a}{l}t)
    $$
-   所以综上
    $$
    \begin{aligned}
     u_n(t,x)&=X_n(x)T_n(t)\\
    &=sin(\frac{n\pi x}{l})(C_ncos(\frac{n\pi a}{l}t)+D_nsin(\frac{n\pi a}{l}t))\quad(n=1,2,\dots)
    \end{aligned}
    $$
    故$u(t,x)$有级数解
    $$
    \begin{aligned}
    u(t,x)&=\sum_{n=1}^{+\infty}u_n(t,x)\\
    &=\sum_{n=1}^{+\infty}(C_ncos(\frac{n\pi a}{l}t)+D_nsin(\frac{n\pi a}{l}t))sin(\frac{n\pi x}{l})
    \end{aligned}
    $$
-   最后确定$C_n和D_n$
    由初始条件得
    $$
    \begin{aligned}
    \varphi(x)&=u(0,x)=\sum_{n=1}^{+\infty}C_nsin(\frac{n\pi x}{l})\\
    \phi(x)&=u_t(0,x)=\sum_{n=1}^{+\infty}\frac{n\pi a}{l}D_nsin(\frac{n\pi x}{l})
    \end{aligned}
    $$
    由正弦展开公式得
    $$
    \begin{aligned}
     C_n&=\frac{2}{l}\int_0^l\varphi(x)sin(\frac{n\pi x}{l})dx\\
    D_n&=\frac{2}{n\pi a}\int_0^l \psi(x)sin(\frac{n\pi x}{l})dx
    \end{aligned}
    $$

> 为何要求级数解？
> 微分方程的解为各部分解的线性组合，由于$n\in N^+$即可，所以有无穷多解，所有解的线性组合就成了级数

# 热传导方程求解
与上基本相同，不再赘述。