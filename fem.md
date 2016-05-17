有限元方法

标签（空格分隔）： 整理笔记及问题

---

## 一 GALERKIN 方法
 有限元方法是GALERKIN方法的一种。GALERKIN 方法是用于求解方程 $$a(u,v)=<f,v>~~~~(1)$$ 
解的近似问题。是用变分原理把问题转化为有限维的问题。
变分原理：对所有的 $$v\in V$$ ,都可找到 $$u\in H_{0}^{1}(\Omega)$$ ,使得 $$a(u,v)=<f,v>$$ 。
这里
$$
a(u,v)=\int_{\Omega}\nabla u\nabla v\mathrm{d}x,<f,v>=\int_{\Omega}fv\mathrm{d}x
$$
GALERKIN 方法是求方程(1)的近似解的方法.
## 二 三角形和重心坐标
 
 1. 网格的两种结构：
 （1）网格的拓扑结构
 （2）几何形状
 2. 单纯形和重心坐标
 $$d+1$$ 个点 $$x_1,x_2,\dots,x_{d+1}$$ 的凸包
$$
\tau:=\{x=\sum_{i=1}^{d+1}\lambda_ix_i|0\leq\lambda_i\leq1,i=1:d+1,\sum_{i=1}^{d+1}\lambda_i=1\}
$$
被定义为一个 $$d+1$$ 维的单纯形。
$$\lambda_1(x),\lambda_2(x),\dots,\lambda_{d+1}(x)$$ 被称为与 $$d+1$$ 个点有关的 $$x$$ 重心坐标。
一维单纯形是一条边；二维单纯形是一个三角形；三维单纯形是四面体。

##三 几个重要的定义
 
 1. 协调和相容
任意两个单纯形的交集是空集或者说单纯的维数比这两个单纯形的维数低，则称为相容或者协调。
例如：相容或者协调，二维的单纯形相交不会出现半条边，他们的交集是一个点或者是一条边.
 2. 规则形状 如果存在一个常数 $$c_0$$ ，使得 
$$
max_{\tau\in T}\frac{diam(\tau)^d}{|\tau|}\leq c_0
$$
也就是说一个 $$d$$ 维单纯形的直径的 $$d$$ 次方除以单纯形的面积的最大值要小于一个常数。
 3. 拟一致
 如果
$$
\frac{max_{\tau\in T}|\tau|}{min_{\tau\in T}|\tau|}\leq p
$$
对于所有的 $$T\in F$$,则称 $$F$$ 为拟一致的。
也就是说单纯形面积的最大值与最小值之比小于等于一个常数，则就称为拟一致。
 4. 基函数
 $$\phi_i$$ 是分段线性的，且对于所有的顶点 $$x_j\in T_h$$ ,有 $$\phi_i(x_j)=\delta_{i,j}$$，则称 $$\phi_i$$ 是基函数。 （也就是如何选取基函数。）
 5. 商空间
 商空间也就是说是一个等价类，例如商空间 $$W^{k+1,p}(\Omega)/P_k(\Omega)$$ ,$$W^{k+1,p}(\Omega)$$中的两个元素相减是属于 $$P_k(\Omega)$$ 的。
 6. 正则性结果
存在一个 $$w\in H_0^2(\Omega)\cap H_0^1(\Omega)$$ 使得

$$a(w,v)=(u-u_h,v)$$

$$||w||_2\leq C||u-u_h||$$

其中， $$u$$ ,$$u_h$$ 分别是连续解和非连续方程的解。

##四 几个定理的证明
 1. 列表项
 **引理3.1：** 
 当 $$\tau$$ 是一个规则形，我们有对于所有的 $$|\alpha|=k$$，
 $$
 ||D^{\alpha}\widehat v||_{0,p,\widehat\tau}\simeq h_{\tau}^{sob_n(k,n)}||D^{\alpha}v||_{0,p,\tau}
 $$
这里sobolev数 $$sob_n(k,n)=k-\frac{n}{p}$$  
证明:
$$
|J^{-1}|=|\frac{\partial \xi_i}{\partial x_j}|\eqsim h^{-n},\tilde{v} (\tilde{x} )=v(x)
$$
$$
||D^{\alpha}\tilde{v}||_{0,p,\tilde{\tau}}=(\int_{\tilde{\tau}}|D^{\alpha}\tilde{v}(\tilde{x})|^{p}\mathrm{d}\tilde{x})^{\frac{1}{p}}\\
=(\int_{\tilde{\tau}}|\frac{\partial ^{\alpha}\tilde{v}(\tilde{x})}{\partial\tilde{x}^{\alpha}}|^{p}\mathrm{d}\tilde{x})^{\frac{1}{p}}\\
\eqsim(|J^{-1}|\int_{\tau}|\frac{\partial ^{\alpha}v(x)}{h^{-|\alpha|}\partial x^{\alpha}}|^{p}\mathrm{d}x)^{\frac{1}{p}}\\
=h^{k-\frac{n}{p}}\int_{\tau}|\frac{\partial ^{\alpha}v(x)}{\partial x^{\alpha}}|^{p}\mathrm{d}x)^{\frac{1}{p}}\\
=h^{k-\frac{n}{p}}(\int_{\tau}|D^{\alpha}v(x)|^{p}\mathrm{d}x)^{\frac{1}{p}}\\
=h_{\tau}^{sob_n(k,n)}||D^{\alpha}v||_{0,p,\tau}
$$
 2. 证明插值算子的性质 
 $$\widehat{u-u_I}=\widehat u-\widehat u_I$$
 
 证明:
 3. 逆估计
 $$|u_h|_{1,\tau}\lesssim h^{-1}||u_h||_{\tau}$$

证明:$$|u_h|_{1,\tau}=\int_{\tau}|u_h|^2\mathrm{d}x\mathrm{d}y$$

$$||u_h||_{0,p,\tau}\lesssim h^{n(\frac{1}{p}-\frac{1}{q})}||u_h||_{1,p,\tau},~~~1\leq q\leq p\leq \infty$$
##五 二维及三维的仿射变换
标准单形到普通单形的映射:$$F:\widehat{\tau}\mapsto\tau$$
可表示为 $$F(\widehat x)=B\widehat x+C$$
 - 二维仿射变换

 令
$$
B=\begin{pmatrix}
b_{11} & b_{12} \\
b_{21} & b_{22}
\end{pmatrix},
C=\begin{pmatrix}
c_1  \\
c_2
\end{pmatrix}
$$

则

$$
\begin{pmatrix}
b_{11} & b_{12} \\
b_{21} & b_{22}
\end{pmatrix}\begin{pmatrix}
1  \\
0
\end{pmatrix}+\begin{pmatrix}
c_1  \\
c_2
\end{pmatrix}=\begin{pmatrix}
x_1  \\
y_1
\end{pmatrix}
$$

$$
\begin{pmatrix}
b_{11} & b_{12} \\
b_{21} & b_{22}
\end{pmatrix}\begin{pmatrix}
0  \\
1
\end{pmatrix}+\begin{pmatrix}
c_1  \\
c_2
\end{pmatrix}=\begin{pmatrix}
x_2  \\
y_2
\end{pmatrix}
$$

$$
\begin{pmatrix}
b_{11} & b_{12} \\
b_{21} & b_{22}
\end{pmatrix}\begin{pmatrix}
0  \\
0
\end{pmatrix}+\begin{pmatrix}
c_1  \\
c_2
\end{pmatrix}=\begin{pmatrix}
x_3  \\
y_3
\end{pmatrix}
$$

所以

$$
B=\begin{pmatrix}
x_1-x_3 & x_2-x_3 \\
y_1-y_3 &y_2-y_3
\end{pmatrix},
C=\begin{pmatrix}
x_3  \\
y_3
\end{pmatrix}
$$

 - 三维仿射变换
 (1)三维空间的标准2单形到普通2单形

$$
B=\begin{pmatrix}
x_1-x_3 & x_2-x_3 \\
y_1-y_3 &y_2-y_3 \\
z_1-z_3& z_2-z_3
\end{pmatrix},
C=\begin{pmatrix}
x_3  \\
y_3 \\
z_3
\end{pmatrix}
$$
 (2)三维空间的标准3单形到普通3单形
 
 $$
B=\begin{pmatrix}
x_1-x_4 & x_2-x_4 & x_3-x_4\\
y_1-y_4 & y_2-y_4 &y_3-y_4\\
z_1-z_4 & z_2-z_4& z_3-z_4
\end{pmatrix},
C=\begin{pmatrix}
x_4  \\
y_4 \\
z_4
\end{pmatrix}
$$

##六 练习

 1.  对 $$n+1$$ 维的指标 $$\alpha$$ 有
 $$
 \int_{\tau}\lambda^{\alpha}(x)\mathrm{d}x=\frac{\alpha!n!}{(|\alpha|+n)!}|\tau|
 $$
这里我们可以从以下的子问题来证明。
（1）当 $$n=1$$ ,$$\tau=[0,1]$$ 时，证明
$$
\int_{0}^{1}x^{\alpha_1}(1-x)^{\alpha_2}\mathrm{d}x=\frac{\alpha_1!\alpha_2!}{(\alpha_1+\alpha_2+1)!}
$$
证明:$$n=1,\tau=[0,1]$$
$$
\begin{align}
&\int_{0}^{1}x^{\alpha_1}(1-x)^{\alpha_2}\mathrm{d}x\\
&=\int_{0}^{1}x^{\alpha_1+1-1}(1-x)^{\alpha_2+1-1}\mathrm{d}x\\
&=B(\alpha_1+1,\alpha_2+1)\\
&=\frac{\alpha_2+1-1}{\alpha_1+\alpha_2+1}B(\alpha_1+1,\alpha_2)\\
&= \dots\dots\\
&=\frac{(\alpha_2+1-1)!(\alpha_1+1-1)!}{(\alpha_1+\alpha_2+1+1-1)!}\\
&=\frac{\alpha_1!\alpha_2!}{(\alpha_1+\alpha_2+1)!}
\end{align}
$$

这里
$$
B(p,q)=\int_{0}^{1}x^{p-1}(1-x)^{q-1}\mathrm{d}x,p>0,q>0\\
B(p,q)=\frac{(q-1)!(p-1)!}{(p+q-1)!}
$$

（2）当 $$n=2$$ ,$$\tau=s^2$$ 时，证明
$$
\int_{\tau}x^{\alpha_1}y^{\alpha_2}(1-x-y)^{\alpha_3}\mathrm{d}x=\frac{\alpha_1!\alpha_2!\alpha_3!}{(\alpha_1+\alpha_2+\alpha_3+1)!}
$$
证明：当 $$n=2,\tau=s^2$$ 时，
$$
\begin{align}
&\int_{\tau}x^{\alpha_1}y^{\alpha_2}(1-x-y)^{\alpha_3}\mathrm{d}x\\
&=\int_{0}^{1}\int_{0}^{1}x^{\alpha_1}y^{\alpha_2}(1-x-y)^{\alpha_3}\mathrm{d}x\mathrm{d}y\\
&=\int_{0}^{1}x^{\alpha_1}\mathrm{d}x\int_{0}^{1-x}y^{\alpha_2}(1-x-y)^{\alpha_3}\mathrm{d}y\\
&=\int_{0}^{1}x^{\alpha_1}\mathrm{d}x\frac{1}{\alpha_2+1}\int_{0}^{1-x}(1-x-y)^{\alpha_3}\mathrm{d}y^{\alpha_2+1}\\
&=\int_{0}^{1}x^{\alpha_1}\mathrm{d}x\frac{\alpha_3}{\alpha_2+1}\int_{0}^{1-x}(1-x-y)^{\alpha_3-1}y^{\alpha_2+1}\mathrm{d}y\\
&=\dots\dots\\
&=\frac{\alpha_3!}{(\alpha_2+1)\dots\dots(\alpha_2+\alpha_3)}\int_{0}^{1}x^{\alpha_1}\mathrm{d}x\int_{0}^{1-x}y^{\alpha_2+\alpha_3}\mathrm{d}y\\
&=\frac{\alpha_1!\alpha_2!\alpha_3!}{(\alpha_1+\alpha_2+\alpha_3+1)!}
\end{align}
$$

（3）证明当 $$\tau=s^n$$ 时
$$
\int_{\tau}\lambda^{\alpha}(x)\mathrm{d}x=\frac{\alpha!n!}{(|\alpha|+n)!}|\tau|
$$
成立。

（4）证明：通过从标准单形 $$\tau=s^n$$ 变换到一般单形 $$\tau$$ 上，
$$
\int_{\tau}\lambda^{\alpha}(x)\mathrm{d}x=\frac{\alpha!n!}{(|\alpha|+n)!}|\tau|
$$
成立。

 2.（1）设 $$n_i$$ 是边 $$e_i$$ 的外法向量，$$d_i$$ 是从 $$x_i$$ 到 $$e_i$$ 的距离。证明
$$
\nabla\lambda_i=-\frac{1}{d_i}\vec n_i
$$
证明：
$$
\nabla\lambda_i\vec e_i=\frac{\lambda(x_i)-0}{d_i}\vec n_i=\frac{1}{d_i}
$$
又方向是从 $$x_i$$ 到 $$e_i$$，所以
$$
\nabla\lambda_i=-\frac{1}{d_i}\vec n_i
$$
（2）设 $$\theta_i$$ 是关于顶点 $$x_i$$ 的角，证明
$$
\int_{\tau}\nabla\lambda_i\nabla\lambda_j\mathrm{d}x=-\frac{1}{2}\cot\theta_k
$$
（3）设 $$c_i=\cot\theta_i,i=1,2,3$$ ,定义一个刚度矩阵 $$A_{\tau}$$ 是 $$3\times3$$ 的，通过 $$\int_{\tau}\nabla\lambda_i\nabla\lambda_j\mathrm{d}x$$ ,证明
$$
A_{\tau}=\frac{1}{2}
\begin{bmatrix}
c_2+c_3   &  -c_3 &  -c_2\\
-c_3   &  c_3+c_1 &  -c_1\\
-c_2   &  -c_1 &  c_1+c_2
\end{bmatrix}
$$

(4)设 $$e$$ 是在 $$T$$ 中的节点 $$x_i$$ ,$$x_j$$ 组成的一个内边,并且是两个单纯形 $$\tau_1$$ 和 $$\tau_2$$ 的公共部分,用 $$\theta_{e}^{\tau}$$ 表示在 $$\tau$$ 中的角的对边 $$e$$ ,则证明 $$a_{ij}=\int_{\Omega}\nabla \phi_i\nabla \phi_j\mathrm{d}x$$ 是
$$
a_{ij}=-\frac{1}{2}(\cot\theta_{e}^{\tau_1}+\cot\theta_{e}^{\tau_2})
$$

$$a_{ij}\leq0$$ 当且仅当 $$\theta_{e}^{\tau_1}+\theta_{e}^{\tau_2}\leq\pi$$

 3.这部分是给出单元来证明误差估计,设 $$\tau$$ 是由顶点 $$x_i,i=1,2,\dots,n+1$$ 组成的单纯形,并且 $$\{\lambda_i,i=1,2,\dots,n+1\}$$ 是对应的重心坐标,辅助函数 
 $$
 g_i(t,x)=u(y(x_i,t,x)),y=x_i+t(x-x_i)
 $$

 (1)证明:
$$
u_I(x)=\sum_{i=1}^{n+1}u(x_i)\lambda_i(x),~\sum_{i=1}^{n+1}\lambda_i(x)=1,且 \sum_{i=1}^{n+1}(x-x_i)\lambda_i(x)=0
$$

(2)对与 $$u\in C^{2}(\overline\tau)$$ ,证明下列误差估计
$$
(u_I-u)(x)=\sum_{i=1}^{n+1}\lambda_i(x)\int_{0}^{1}tg''_i(t,x)\mathrm{d}t\\
\nabla(u_I-u)(x)=\sum_{i=1}^{n+1}\nabla\lambda_i(x)\int_{0}^{1}tg''_i(t,x)\mathrm{d}t
$$
由 $$\lambda_i$$ 和 $$i$$ 的求和可得
$$
g_i(0,x)=g_i(1,x)-g'_i(1,x)+\int_{0}^{1}tg''_i(t,x)\mathrm{d}t
$$

(3)设 $$u\in W^{2,p}$$ ,$$p>\frac{n}{2}$$.证明
$$
||u-u_I||_{0,p}\leq C_{p,n}h^2|u|_{2,p}
$$

这里 $$C_{p,n}=p(n+1)/(2p-n)$$ 且 
$$
|u-u_I|_{1,p}\leq Ch|u|_{2,p}
$$