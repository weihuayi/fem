#sobolev space

### 1.1预备知识: 
 

 1. **设立讨论的环境:利普希茨区域,多重导数和一些基本的函数空间** 
 
 (1)利普希茨区域的定义:如果 $$\Omega$$ 的边界能被利普希茨连续函数局部代替,则称 $$\Omega$$ 为一个利普希茨区域.即对任意的 $$x\in\partial\Omega$$ ,存在 $$x$$ 的一个邻域,使得 $$G\cap\partial\Omega$$ 在一个适当的坐标系下是一个利普希茨连续函数.

(2)利普希茨函数:满足利普希茨条件的函数.

(3)利普希茨条件:
 
$$
|f(x_2)-f(x_1)|\leq L|x_2-x_1|,
$$

其中 $$L$$ 为利普希茨常数.
 
2.(1)**一些利普希茨区域的例子:**
 
 所有光滑的区域是利普希茨区域;
 非光滑区域的例子:在 $$R^2$$ 内的每一个多边形和 $$R^3$$ 内的每一个多面体都是利普希茨区域;在 $$R^n$$ 内每一个凸区域都是利普希茨区域(凸区域:区域上任意两点的连线都在区域内,则这样的区域就是凸区域).

(2)**非利普希茨区域的例子:**

两个多边形相交仅仅只有一个顶点,一个区域在边界上有一个交点.
 
 3.**偏导数算子:**
 
 设 $$\alpha=(\alpha_1,\alpha_2,\dots,\alpha_n)\in Z_{+}^{n}$$ 是一个非负整数的向量,这里 $$Z_{+}^{n}$$ 是非负整数的集合.
 $$|\alpha|=\sum_{i=1}^{n}\alpha_i$$ .对于一个连续函数 $$v$$ 和 $$x=(x_1,x_2,\dots,x_n)\in R^n$$ ,用
$$

D^{\alpha}v=\frac{\partial^{|\alpha|}v}{\partial x_1^{\alpha_1}\dots x_n^{\alpha_n}},
$$
且

$$

x^{\alpha}=x_1^{\alpha_1}\dots x_n^{\alpha_n}.
$$
 4.**常用的几个banach空间**

(1) $$C(\overline\Omega)$$ 是一个连续函数的空间,

$$

||v||_{C(\overline\Omega)}=max_{x\in\overline\Omega}|v(x)|
$$

(2) $$C_{0}^{\infty}(\Omega)$$ 是无穷可微函数空间,

$$
supp(v)=closure~of \{x\in\Omega:v(x)\neq 0\}
$$

(3) $$E(\Omega)$$ 是表示 $$u=v$$ 几乎处处成立的局部勒贝格可积函数的空间.

(4) $$
L^p=\{v\in E(\Omega):\int_{E(\Omega)}|v|^p\mathrm{d}x<\infty\}$$ 
是 $$p$$ 方可积函数空间,且范数定义为:

$$
||u||_{p,\Omega} =(\int_{\Omega}|u|^p\mathrm{d}x)^{\frac{1}{p}},1\leq p<\infty
$$

$$
||u||_{\infty,\Omega}=ess sup_{\Omega}|u|
$$

本质上确界(ess sup)
设 $$f(x)$$ 是 $$E\in R^n$$ 上的可测函数,$$m(E)>0$$ .若存在 $$M$$ ,使得 $$f(x)<M$$ ,则称 $$E$$ 上本性有界,$$M$$ 称为 $$f(x)$$ 的本性上界。在对一切本性上界取下确界，记为 $$||f||_{\infty}$$ ,称它为 $$f(x)$$ 在 $$E$$ 上的本性上确界.此时用 $$L^{\infty}(E)$$ 表示在 $$E$$ 上的本性有界的函数. 
(**本质上界与上界的区别:本质上界是最小的上确界,除了0测度集之外的函数.**)
 
 5.**散度定理:
 $$
\int_{\Omega}div\vec F\mathrm{d}x=\int_{\partial \Omega}\vec F\vec n\mathrm{d}s
$$**

例:用散度定理求一个多面体的体积.
$$
\begin{align}
&\int_{\Omega}1\mathrm{d}x\\
&=\frac{1}{3}\int_{\Omega}div
\begin{pmatrix}
x  \\
y  \\
z
\end{pmatrix}
\mathrm{d}x\\
&=\frac{1}{3}\int_{\partial\Omega}div
\begin{pmatrix}
x  \\
y  \\
z
\end{pmatrix}\vec n_s
\mathrm{d}s\\
&=\frac{1}{3}\int_{\partial\Omega}
[\begin{pmatrix}
x  \\
y  \\
z
\end{pmatrix}-\begin{pmatrix}
x_1  \\
y_1  \\
z_1
\end{pmatrix}+\begin{pmatrix}
x_1  \\
y_1  \\
z_1
\end{pmatrix}]\vec n_s
\mathrm{d}s\\
&=\frac{1}{3}\int_{s_1+s_2+s_3}
\begin{pmatrix}
x_1  \\
y_1  \\
z_1
\end{pmatrix}\vec n_s
\mathrm{d}s\\
\end{align}
$$
 6.**Banach空间:** 完备的赋范线性空间.

**赋范线性空间:**

(1) $$||x||\geq 0$$ 且 $$||x||= 0\Leftrightarrow x=0$$

(2) $$||x+y||\leq ||x||+||y||$$

(3) $$||\alpha x||=\alpha||x||$$
 
 **Hilbert空间:**完备的内积空间.(按内积诱导下的范数完备)
完备:空间中的每个柯西点列都收敛.

**内积空间:** $$X$$ 是复线性空间,对于 $$X$$ 中的任意两点 $$x,y$$ 都有一复数 $$<x,y>$$ 与之对应,且满足:

(1) $$<x,x>\geq0$$,且$$<x,x>=0\Leftrightarrow x=0$$

(2) $$<\alpha x+\beta 
y,z>=\alpha<x,z>+\beta<y,z>$$

(3) $$\overline{<x,y>}=<y,x>$$


###1.2 sobolev空间的定义
sobolev空间从分数阶和整数阶来定义的.在整数阶是用广义函数的它的弱导数的概念来定义的;分数阶是通过介绍 $$p$$ 方可积的差商来定义的.

 1.  **广义函数和弱导数**

**广义函数:**

显然 $$C_{0}^{\infty}(\Omega)$$ 是一个实向量空间,并由一个适当的拓扑转换成拓扑空间, $$C_{0}^{\infty}(\Omega)$$具有以下的拓扑,用 $$D(\Omega)$$ 来表示:一个函数序列 $${\phi_k}\subset C_{0}^{\infty}(\Omega)$$ 被成为收敛于函数 $$\phi\subset C_{0}^{\infty}(\Omega)$$ ,如果满足以下两个条件:

(1)存在一个紧集 $$K\subset \Omega$$ ,使得对于所有的 $$k$$ , $$supp(\phi_k-\phi)\subset K$$

(2)对任意的 $$\alpha\in Z_{+}^{n}$$ ,都有
$$
\lim_{k\to \infty}||D^{\alpha}(\phi_k-\phi)||_{\infty}=0
$$

**弱导数:**

$$u$$ 是一个连续函数,对任意的 $$\alpha\in Z_{+}^{n}$$ ,都有
$$
\int_{\Omega}D^{\alpha}u(x)\phi(x)\mathrm{d}x=(-1)^{|\alpha|}\int_{\Omega}u(x)D^{\alpha}\phi(x)\mathrm{d}x,
$$

对所有的 $$\phi\in D(\Omega)$$
如果 $$T\in D'(\Omega)$$ ,对任意的 $$\alpha\in Z_{+}^{n}$$ ,定义弱导数 $$D^{\alpha}T$$,
$$
<D^{\alpha}T,\phi>=(-1)^{|\alpha|}<T,D^{\alpha}\phi>,对所有的 \phi\in D(\Omega)
$$

 **紧集:** 
 
 $$X$$ 是度量空间, $$M$$ 是 $$X$$ 的一个子集, $$M$$ 中的任何点列 $${x_n}$$ 都存在子列收敛于 $$M$$ 中的一元素 $$x_0$$ .

**关系:** 紧集一定是闭集,闭集不一定是紧集;紧集一定是完备集,完备集不一定是紧集;完备集一定是闭集,闭集不一定是完备集; $$R^n$$ 中有界闭集必为紧集;有限维空间中紧集和有界闭集等价.

(1)闭集:集合 $$A$$ 中的每一个聚点都属于 $$A$$ .

(2)紧集: $$X$$ 中的每个覆盖 $$A$$ 的开集族中必有有限个开集覆盖 $$A$$ .

(3)完备集:若 $$A=A'$$ ,则 $$A$$ 为完备集.

 2.**$$\delta$$ 函数:**
$$
\int_{\Omega}\delta(x)\phi(x)\mathrm{d}x=\phi(0)
$$

($$\delta$$ 函数不能看成是一个局部可积的函数)
一般而言,弱导比经典导更弱,以至于可以把微分算子从函数微分扩大到更大的空间(分布空间).
例:对于 Heaviside 分段函数
$$
S(x)=\begin{cases}
1   &x>0\\
0   &x<0
\end{cases}
$$

通过定义

$$
\int_{R}S'\phi\mathrm{d}x=-\int_{R}S\phi'\mathrm{d}x=\phi(0)
$$

因此在分布意义下 $$S'=\delta$$ .但是 $$\delta \notin L_{loc}^{1}(\Omega)$$ .

**练习**

证明 $$\delta$$ 函数不能由任何局部可积函数按式(1)给出

证: 假设存在局部可积函数 $$f(x)$$ ，使得 
$$
\delta(\phi)=\phi(0)=\int_{R}f(x)\phi(x)\mathrm{d}x,\forall \phi \in D(R)
$$

特别的取函数$$\phi(x)$$ 为 
$$
\phi(x,a)=\begin{cases}
e^{-\frac{a^2}{a^2-|x|^2}}, & |x|< a \\
0, & |x|\geq a
\end{cases}
$$

其中 $$a>0$$ 为常数.由此可知 $$\phi(x,a)\in C_{c}^{\infty}(R)$$.依上述假定可见 
$$
\int_{R}f(x)\phi(x,a)\mathrm{d}x=\phi(0,a)=e^{-1}
$$

但上式左端的积分满足 
$$
|\int_{R}f(x)\phi(x)\mathrm{d}x|=|\int_{|x|<a}f(x)e^{-\frac{a^2}{a^2-|x|^2}}\mathrm{d}x|\\
\leq\int_{|x|<a}|f(x)|\mathrm{d}x\to 0,a\to 0
$$

所以上面两式矛盾。
故 $$delta$$ 函数不能由任何局部可积函数按式$$<T_u,\phi>=\int_{R}u\phi\mathrm{d}x$$ 给出，它是奇异的广义函数，而不是“普通(ordinary)”的广义函数。

3.**整数阶的sobolev空间**

(1) $$(k,p)$$ 是sobolev空间的指数, $$k$$ 是非负整数, $$p\geq 1$$ ,定义
$$
W^{k,p}(\Omega)=\{v\in L^p(\Omega):D^{\alpha}v\in  L^p(\Omega) for    ~all|\alpha|\leq k \}
$$

范数:
$$
||v||_{k,p,\Omega}^{p}:=\sum_{|\alpha|\leq k}||D^{\alpha}v||_{0,p,\Omega}^{p}
$$

当 $$p=2$$ 时,习惯的写为 $$^{k}(\Omega)=W^{k,2}(\Omega)$$,$$H^{k}(\Omega)$$ 是带有内积希尔伯特空间,
$$
(u,v)=\sum_{|\alpha|\leq k}(D^{\alpha}u,D^{\alpha}v),
$$

对应的范数
$$
||v||_{k,\Omega}=||v||_{k,2,\Omega}
$$

(2)定义
$$
W_{loc}^{k,p}(\Omega)=\{u\in E(\Omega):for~any~U\subset \subset\Omega, u\in W^{k,p}(U) \}
$$

且 $$H_{loc}^{k}(\Omega)=W_{loc}^{k,2}(\Omega)$$
对于 $$L^{p}(\Omega)$$ 上的一个函数,它的弱导总是存在的,但是它的弱导不在空间 $$L^{p}(\Omega)$$ 中,因此在 $$W^{k,p}(\Omega)$$ 中的元素有一定的光滑性.
 
 4.$$
 W_{loc}^{k,p}(\Omega)=\{u\in E(\Omega):for~all~U\subset \subset\Omega, u\in W^{k,p}(U) \}
 $$
 
且 $$H_{loc}^{k}(\Omega)=W_{loc}^{k,2}(\Omega)$$
其中 $$\subset \subset\Omega$ 也即 $\overline U \subset\Omega$$
当 $$p=2 $$ 时, $$H_{loc}^{k}(\Omega)=W_{loc}^{k,2}(\Omega)$$
当 $$p\neq2$$ 时, $$W_{loc}^{k,2}(\Omega)$$ 是Banach空间.
 
5.**分数阶sobolev空间**

 古典导数的定义是通过逐点求差商的极限.对于sobolev空间的函数,我们用差商的 $p$ 方可积描述它的可微性.

(1)对于 $$0<\theta<1$$ , $$1\leq p<\infty$$ ,定义
$$
W^{\theta,p}(\Omega)=\{v\in L^p(\Omega):\int_{\Omega} \int_{\Omega}\frac{|v(x)-v(y)|^p}{|x-y|^{n+\theta p}}\mathrm{d}x\mathrm{d}y<\infty\}
$$

且 $$H^{\theta}(\Omega)=W^{\theta,2}(\Omega)$$
在 $$W^{\theta,p}(\Omega)$$ 中,定义如下半范数和范数:
$$
|v|_{\theta,p,\Omega}^p:=\int_{\Omega}\int_{\Omega}\frac{|v(x)-v(y)|^p}{|x-y|^{n+\theta p}}\mathrm{d}x\mathrm{d}y
$$

$$
||v||_{\theta,p,\Omega}^p:=||v||_{0,p,\Omega}^p+|v|_{\theta,p,\Omega}^p
$$

例:已知函数
$$
s(x)=\begin{cases}
1, & x>0 \\
0, & x<0
\end{cases}
$$

对于不等式
$$
\int_{\Omega}\int_{\Omega}\frac{|v(x)-v(y)|^p}{|x-y|^{n+\theta p}}\mathrm{d}x\mathrm{d}y<\infty
$$

利用坐标变换 $$\overline x =x-y$$ , $$\overline y =x+y$$ 得
$$ 
\int_{0}^{1}\frac{1}{\overline x^{\theta p}}\mathrm{d}{\overline x}<\infty
$$

这里要求 $$\theta<\frac{1}{p}$$ .特别的,我们可以推出 $$S\in H^{1/2-\varepsilon}(-1,1)$$ ,对任意的 $$\varepsilon \leq 1/2$$ ,但是
$$S\notin H^{1/2-\varepsilon}(-1,1)$$ .

(2)给出 $$s=k+\theta$$,$$\theta \in(0,1),k\geq0$$ ,定义
$$
W^{s,p}(\Omega)=\{v\in W^{k,p}(\Omega):D^{\alpha}v\in  W^{\theta,p}(\Omega) ~|\alpha|\leq k \}
$$

在 $$W^{s,p}(\Omega)$$ 中,定义半范数和范数:
$$
|v|_{s,p,\Omega}^p:=(\sum_{|\alpha|=k}|D^{\alpha}v|_{\theta,p,\Omega}^p)^\frac{1}{p}
$$

$$
||v||_{s,p,\Omega}^p:=(\sum_{|\alpha|\leq k}||D^{\alpha}v||_{\theta,p,\Omega}^p)^\frac{1}{p}
$$

 6.**负数阶sobolev空间**
 
 对于 $$k\in N$$ , $$W^{-k,p}(\Omega)$$ 被定义为对偶空间 $$W_{0}^{k,p'}(\Omega)$$ , $$p'$$ 是 $$p$$ 的共轭,即 $$\frac{1}{p}+\frac{1}{p'}=1$$ .特别的对于任意的 $$f\in H^{-1}(\Omega)$$ ,
$$
H^{-k}(\Omega)=( H_{0}^{-k}(\Omega))'
$$

$$
||f||_{-1,\Omega}=sup_{v\in H_{0}^{1}(\Omega)}\frac{<f,v>}{||v||_{1,\Omega}}
$$

定理1.9:设 $$v\in D'(\Omega)$$,则 $$v\in W^{k,p}(\Omega)$$ 当且仅当 
$$
v=\sum_{|\alpha|\leq k}D^{\alpha}v_{\alpha},
$$

对任意的 $$v_{\alpha}\in L^p(\Omega)$$
注意: $$C_{0}^{\infty}(\Omega)$$ 在 $$W^{k,p}(\Omega)$$ 中不稠密,因此 $$W^{k,p}(\Omega)$$ 的对偶空间不能作为广义函数的子空间嵌入.

7.**用傅里叶变换描述sobolev空间**
 给出 $$v\in H^{k}(R^n)$$ ,显然 $$\widehat {D^{\alpha}v}=(i\xi)^{\alpha}\widehat v$$ (根据傅里叶公式推出)
证明: 傅里叶变换公式:
(1)
$$
\widehat {f(x)}=\int_{R^n}f(x)e^{-\xi ix}\mathrm{d}x
$$
(2)
$$
\widehat {Df(x)}=\xi  ix_k\widehat {f(x)}
$$
从而
$$
\widehat {Df(x)}=\int_{R^n}e ^{-i\xi x}\xi \mathrm{d}x=  i\xi \widehat {f(x)}
$$
所以
$$
\widehat {D^2f(x)}=\widehat {D( {Df(x)})}=\xi i\widehat {Df(x)}=(\xi i)^2\widehat {f(x)}
$$
......
$$
\widehat {D^{\alpha}f(x)}=(\xi i)^{\alpha}\widehat {f(x)}
$$
 
 所以有

 $$
 ||\widehat {D^{\alpha}f(x)}||_{0,R^n}=||\xi^{\alpha}\widehat {f(x)}||_{0,R^n}
 $$
这样,定义

$$
||v||_{k,R^n}^{2} =\int_{R^n}(\sum_{|\alpha|\leq k}|\xi|^{2\alpha})|\widehat v(\xi)|^2\mathrm{d}\xi,
$$

用基本不等式

$$
(1+|\xi|^2)^k \lesssim\sum_{|\alpha|\leq k}(|\xi|^2)^{\alpha}\lesssim(1+|\xi|^2)^k
$$

可以推出

$$
||v||_{k,R^n}\simeq||(1+|.|^2)^{\frac{k}{2}}\widehat v||_{0,R^n}
$$

$pf:$
$$
||v||_{k,R^n}\\=(\int_{R^n}(\sum_{|\alpha|\leq k}|\xi|^{2\alpha})|\widehat v(\xi)|^2\mathrm{d}\xi)\\ \simeq  (\int_{R^n}(1+|\xi|^2)^k|\widehat v(\xi)|^2\mathrm{d}\xi)^{\frac{1}{2}}\\ \simeq(\int_{R^n}((1+|\xi|^2)^{k/2}|\widehat v(\xi)|)^2\mathrm{d}\xi)^{\frac{1}{2}}\\ \simeq||(1+|.|^2)^{\frac{k}{2}}\widehat v||_{0,R^n}
$$

这个关系说明sobolev空间 $H^{k}(R^n)$ 可以等价的定义为

$$
H^{k}(R^n)=\{v\in L^{2}(R^n),(1+|\xi|^2)^{\frac{k}{2}}\overline v\in L^{2}(R^n)\}
$$

这可以用来描述实数指数的sobolev空间.
即对任意的 $s\in[0,\infty)$ ,sobolev空间 $H^{s}(R^n)$ 可以定义如下:

$$
H^{s}(R^n)=\{v\in L^{2}(R^n),(1+|\xi|^2)^{\frac{s}{2}}\overline v\in L^{2}(R^n)\}
$$
范数:

$$
||v||_{s,R^n}:=||(1+|.|^2)^{\frac{s}{2}}\overline v||_{0,R^n}
$$

例1.11说明 $\delta$ 函数是 $H^{s}(\Omega)$ 上的一个连续线性泛函;空间维数大时, $H_{0}^{1}(\Omega)$ 不够光滑,不能作为一个有界线性泛函.

###1.3延拓定理
延拓定理是sobolev空间最基础的结论.傅里叶变换是一个有用的工具.但是它仅仅只能用于整个 $$R^n$$ 空间内的函数.我们一般研究的是在
$$\Omega \subset R^n$$ 中,为了从 $$$R^n$$ 空间到有界区域 $\Omega$ 的结果一般化,我们将定义在 $W^{k,p}(\Omega)$ 的函数延拓到 $W^{k,p}(R^n)$ 中.这里只给出结果.
延拓定理:对于任意有界的利普希茨区域 $$\Omega$$ ,任意 $$s\geq 0$$ , $$1\leq p<\infty$$ ,存在一个线性算子 $$E$$ : $$W^{s,p}(\Omega)\to W^{s,p}(R^n)$$ ,使得
(1) $$Eu|_{\Omega}=u$$
(2) $$E$是连续的.即存在一个与 $$s\geq 0$$ 有关的常数 $$C(s,\Omega)$$ ,使得对任意 $$1\leq p\leq\infty$$ ,有

$$
||Ev||_{s,p,\Omega}\leq C(s,\Omega)||v||_{s,p,\Omega}
$$

###1.4嵌入定理

 1. 对于两个巴拿赫空间 $$B_1,B_0$$ ,称 $B_1$ 是连续的嵌入到 $B_0$ .如果对任意 $u\in B_1$ ,则 $u\in B_0$ ,
 且是连续的.即对于所有的 $u\in B_1$ ,有 $||u||_{B_0}\lesssim||u||_{B_1}$ .
 2. 定理1.15
 **一般的sobolev嵌入:**
 $1\leq p\leq\infty$,$k\in Z_{+}$ ,且 $\Omega$ 是 $R^n$ 上的一个有界的利普希茨区域.
 (1)若 $kp>n$,
则 $W^{k,p}(\Omega)\hookrightarrow C(\overline{\Omega})$
 (2)若 $kp=n$,
则 $W^{k,p}(\Omega)\hookrightarrow L^{q}(\Omega)$,$q\in[1,\infty)$
特别的, $W^{n,1}(\Omega)\hookrightarrow C(\overline{\Omega})$
(3)若 $kp<n$,
则 $W^{k,p}(\Omega)\hookrightarrow L^{q}(\Omega)$,$\frac{1}{q}=\frac{1}{p}-\frac{k}{n}$
 3. 用 $x$ 轴对应 $L^p$ 空间,用 $y$ 轴对应光滑性,在第一象限内,过点 $(\frac{1}{p},0)$ 且斜率为 $n$ 的直线,在这条直线的上半部分可以嵌入到 $L^p$ 空间,下半部分不能嵌入到 $L^p$ 空间.那么如果在直线上点是否可以嵌入到 $L^p$ 空间?为了快速的确定一个点是否在界线上,我们介绍
 
 $$
 sob_{n}(k,p)=k-\frac{n}{p}
 $$
 
如果 $sob_{n}(k,p)>0$ ,则 $W^{k,p}(\Omega)$ 空间上的函数是连续的.一般的,

$$
W^{k,p}(\Omega)\hookrightarrow W^{l,q}(\Omega),if~k>l~and~sob_{n}(k,p)>sob_{n}(l,p)
$$
sobolev空间上对应界线上的点是否可以嵌入到 $L^p$ 空间.例如, $n\geq1$ ,
 $W^{n,1}(\Omega)\hookrightarrow L^{\infty}(\Omega)$ ,
但是 $W^{1,n}(\Omega)$ 不能嵌入到 $L^{\infty}(\Omega)$

###1.5 迹定理

 1. 定理1.19:设 $\Omega\subset R^n$ 是一个连续有界的利普希茨区域.迹算子 $\gamma:C^1(\overline\Omega)\mapsto C(\Gamma)$ 可以连续的延拓到 $\gamma:H^1(\Omega)\mapsto H^{\frac{1}{2}}(\Gamma)$ ,
即迹不等式:
 
$$
||\gamma(u)||_{\frac{1}{2},\Gamma}\lesssim||u||_{1,\Omega},
$$

对于所有的 $u\in H^1(\Omega) $
迹算子是满射且它有一个连续的逆算子.

###1.6范数等价定理
 1. 对 $i\leq k+1$ , 定义一个范数 $||.||_{k+1,p}$ 包含所有的 $i$ 阶弱导,可以证明对所有的 $u\in W^{k+1,p}(\Omega)$ ,有
$$
||u||_{k+1,p}\simeq||u||_{0,p}+|u|_{k+1,p}
$$
考虑下边这个分解:
$$
W^{k+1,p}(\Omega)=P(\Omega)\oplus(W^{k+1,p}/P(\Omega))
$$
差商空间 $(W^{k+1,p}/P(\Omega))$ :表示 $W$ 中的任意两个元素相减是 $P(\Omega)$ 中的元素.
 2. 定理1.20:对任意的 $u\in W^{k+1,p}(\Omega)$ ,有
$$
inf_{p \in \rho _k(\Omega)}||u+p||_{k+1,p,\Omega}\simeq|u|_{k+1,p,\Omega}
$$

在多项式空间中,由于他是有限维的,所以范数 $||.||_{0,p}$ 可以被多项式空间 $\rho _k(\Omega)$ 的其他范数定义.
一般的,我们在 $W^{k+1,p}(\Omega)$ 上的半范数  $F(.)$ ,即
$$
F:W^{k+1,p}(\Omega)\to R^{+}
$$

且
$$
F(u+v)\leq F(u)+F(v),F(\alpha u)\leq |\alpha|F(u)
$$

范数有一个条件:对 $p\in \rho _k(\Omega),F(p)=0$ ,当且仅当 $p=0$
 3. 如果 $u_k\to u$ in $W^{k+1,p}(\Omega)$,则
 $$F(u)\leq\lim_{k\to \infty}\inf F(u_k)$$

证明:由于 $L^2$ 范数的弱下半连续性可得
$$\int_{\Omega}|\nabla v|^2\mathrm{d}x\leq\lim_{k\to \infty}\int_{\Omega}|\nabla v_k|^2\mathrm{d}x$$

又由 $\{v_k\}$ 的弱收敛性得
$$J(v_k)=\frac{1}{2}\int_{\Omega}|\nabla v_k|^2\mathrm{d}x-\int_{\Omega}fv_k\mathrm{d}x$$

两边同时取下极限得
$$\underline{\lim}_{k\to\infty}J(v_k)=\frac{1}{2}\underline{\lim}_{k\to\infty}\int_{\Omega}|\nabla v_k|^2\mathrm{d}x-\underline{\lim}_{k\to\infty}\int_{\Omega}fv_k\mathrm{d}x\\
=\frac{1}{2}\int_{\Omega}|\nabla v|^2\mathrm{d}x-\int_{\Omega}fv\mathrm{d}x\\
=J(v)$$

所以 $$F(u)\leq\lim_{k\to \infty}\inf F(u_k)$$
 4. sobolev范数等价定理
 定理1.21:如果 $F$ 是一个在 $W^{k+1,p}(\Omega)$ 连续的半范数使得对 $p\in \rho_k(\Omega),F(p)=0$ ,当且仅当 $p=0$ ,则
$$
||u||_{k+1,p,\Omega}\simeq|u|_{k+1,p,\Omega}+F(u),
$$

对所有的 $u\in W^{k+1,p}(\Omega)$
 5. 证明Friedriches inequality
 $$||v||_{1,p,\Omega}\lesssim|v|_{1,p,\Omega}+|\int_{T}v\mathrm{d}s|$$
 
对于所有的 $v\in W^{1,p}(\Omega)$
要证明这个不等式需要用到下边的定理:
**定理:**
设 $P_k(\Omega)(k\geq0)$ 为 $\Omega$ 上次数 小于等于 $k$ 的多项式的全体, $N=dimP_k(\Omega)$,又设 $f_i\in(W^{k+1,p}(\Omega))',i=1,2,\dots,N,p\in[1,\infty]$ ,使得当  $f_i(q)=0,\forall1\leq i\leq N,q\in P_k(\Omega)$ 时,就有 $q=0$ ,则存在常数 $C_{\Omega}$ 使得
$$||v||_{k+1,p,\Omega}\lesssim|v|_{k+1,p,\Omega}+\sum_{i=1}^{N}|f_i(v)|$$

证明:反证法证.假设定理不成立,则对每个 $n$ 存在 $v_n$ 使得
$$||v||_{k+1,p,\Omega}=1\\
|v|_{k+1,p,\Omega}+\sum_{i=1}^{N}|f_i(v)|<\frac{1}{n}$$

由于 $\{v_n\}$ 是 $W^{k+1,p}(\Omega)$ 中的有界序列,根据嵌入定理,$W^{k+1,p}(\Omega)\subset\subset W^{k,p}(\Omega)$ ,知存在子序列,仍记为 $\{v_n\}$ 使得 $v_n$ 在 $W^{k,p}(\Omega)$ 中收敛,即得
$$||v_n-v_m||_{k,p,\Omega}\to 0,n,m\to \infty$$

由$$|v|_{k+1,p,\Omega}+\sum_{i=1}^{N}|f_i(v)|<\frac{1}{n}$$知
$$|v_n-v_m|_{k+1,p,\Omega}\leq|v_n|_{k+1,p,\Omega}+|v_m|_{k+1,p,\Omega}\to 0$$

所以 $\{v_n\}$ 是 $W^{k+1,p}(\Omega)$ 中的柯西序列.由是 $W^{k+1,p}(\Omega)$ 中的完备性得,存在 $v\in W^{k+1,p}(\Omega)$ ,使得在 $W^{k+1,p}(\Omega)$ 中 $v_n\to v$
所以
$$|v|_{k+1,p,\Omega}+\sum_{i=1}^{N}|f_i(v)|=0$$

从而
$$|v|_{k+1,p,\Omega}=0$$

即 $v\in P_k(\Omega)$ ,且 $|f_i(v)|=0$ ,由假设得 $v=0$ ,这与 $||v||_{k+1,p,\Omega}=1$ 矛盾,所以假设不成立.得证.
证明不等式:在此定理中令 $k=0,p_2=2$
$$f_1(v)=\int_{\partial{\Omega}}v\mathrm{d}{\delta}$$

则有
$$|f_1(v)|\leq |\partial{\Omega}|^{1/2}||v||_{0,\partial{\Omega}}\leq C_{\Omega}||v||_{1,\Omega}$$

即 $f_1\in (H^1(\Omega))'$ ,又若 $0\neq q_0\in P_0(\Omega)$ ,则
$$f_1(q_0)=q_0|\partial{\Omega}|\neq 0$$

从而由上述定理可得证明.
同理可证 $T_0\subset \partial{\Omega}$ 且 $T_0>0$ 有
$$||v||_{1,\Omega}\lesssim|v|_{1,\Omega}+|\int_{T_0}v\mathrm{d}s|$$

#椭圆边界问题

 1. Dirichlet问题:
\begin{cases}
-\bigtriangleup u+bu=f & in ~~~\Omega \\
u=g, &   on ~~~\partial\Omega
\end{cases}
其中 $b\in L^{\infty}(\Omega),b\geq 0,f\in L^2(\Omega)$
边界条件:
根据变分形式可选择试探函数空间和检验函数空间分别为
$$U=H_{0}^{1}(\Omega),V=H_{0}^{1}(\Omega)$$
 2. Nemann问题
 \begin{cases}
-\bigtriangleup u=f & in ~~~\Omega \\
u|_{\partial\Omega}=g, &   on ~~~\partial\Omega
\end{cases}
其中 $b\in L^{\infty}(\Omega),b\geq 0,f\in L^2(\Omega)$
边界条件:
根据变分形式可选择试探函数空间和检验函数空间分别为
$$U=H^{1}(\Omega)/R,V=H^{1}(\Omega)$$
即两个函数相差一个常数.
 3. 定理2.2设 $f\in L^2(\Omega)$,则$-\bigtriangleup u=f~~~in~~~  L^2(\Omega)$.即
 $$\int_{\Omega}-\bigtriangleup uv\mathrm{d}x=\int_{\Omega}fv\mathrm{d}x$$
$u$满足在边界上为0,且在边界上$\nabla u\vec n=0$.
证明:当 $f\in L^2(\Omega),<f,v>=(f,v)$ .选择 $v\in C_{0}^{\infty}\subset V$
则
$$<-\bigtriangleup u,v>=(f,v),\forall v\in  C_{0}^{\infty}$$

即 $-\bigtriangleup u$ 在分布意义下等于 $f\in L^2(\Omega)$ .
由于 $C_{0}^{\infty}$ 在 $ L^2(\Omega)$ 稠密,且在 $ L^2(\Omega)$ 连续,所以可以推出
 $$\int_{\Omega}-\bigtriangleup uv\mathrm{d}x=\int_{\Omega}fv\mathrm{d}x$$

当 $-\bigtriangleup u\in L^2(\Omega)$ ,对任意的 $v\in H^1$ 有
$$int_{\Omega}\nabla u\nabla v\mathrm{d}x=-\int_{\Omega}-\bigtriangleup uv\mathrm{d}x+\int_{\partial\Omega}\frac{\partial u}{\partial{\vec n}}v\mathrm{d}S$$

所以
$$\int_{\partial\Omega}\frac{\partial u}{\partial{\vec n}}v\mathrm{d}S=0$$

由 $v$ 的任意性可得 $\nabla u\vec n=0$ .
 4. 证明
 $$\widehat{D^{\alpha}v}(\xi)=(i\xi)^{\alpha}\widehat v(\xi)=-(i\xi)^{\alpha}|\xi|^{-2}\widehat{\bigtriangleup v}(\xi)$$
证明:由傅里叶变换公式:
$$
\widehat {f(x)}=\int_{R^n}f(x)e^{-\xi ix}\mathrm{d}x
$$

得
$$\widehat {D^{\alpha}v}=(i\xi)^{\alpha}\widehat v$$

又
$$\widehat{\bigtriangleup v}(\xi)=\widehat{v_{xx}}(\xi)+\widehat{v_{yy}}(\xi)\\
=(i\xi)^{(2,0)}\widehat{v}(\xi)+(i\xi)^{(0,2)}\widehat{v}(\xi)\\
=-\xi_1^2\widehat{v}(\xi)-\xi_2^2\widehat{v}(\xi)\\
=-(\xi_1^2+\xi_2^2)\widehat{v}(\xi)\\
=-|\xi|^2\widehat{v}(\xi)$$

所以
$$\widehat{v}(\xi)=-|\xi|^{-2}\widehat{\bigtriangleup v}(\xi)$$

所以有
$$\widehat{D^{\alpha}v}(\xi)=(i\xi)^{\alpha}\widehat v(\xi)=-(i\xi)^{\alpha}|\xi|^{-2}\widehat{\bigtriangleup v}(\xi)$$
 **问题一:变换过程:** 例:已知函数,

$$
s(x)=\begin{cases}
1, & x>0 \\
0, & x<0
\end{cases}
$$

对于不等式

$$
\int_{\Omega}\int_{\Omega}\frac{|v(x)-v(y)|^p}{|x-y|^{n+\theta p}}\mathrm{d}x\mathrm{d}y<\infty
$$

利用坐标变换 $\overline x =x-y$ , $\overline y =x+y$ 得

$$ 
\int_{0}^{1}\frac{1}{\overline x^{\theta p}}\mathrm{d}{\overline x}<\infty
$$

这里要求 $\theta<\frac{1}{p}$ .特别的,我们可以推出 $S\in H^{1/2-\varepsilon}(-1,1)$ ,对任意的 $\varepsilon \leq 1/2$ ,但是
$S\notin H^{1/2-\varepsilon}(-1,1)$ .
**问题二:证明定理1.9**
定理1.9:设 $v\in D'(\Omega)$,则 $v\in W^{k,p}(\Omega)$ 当且仅当 

$$
v=\sum_{|\alpha|\leq k}D^{\alpha}v_{\alpha},
$$

对任意的 $v_{\alpha}\in L^p(\Omega)$
注意: $C_{0}^{\infty}(\Omega)$在$W^{k,p}(\Omega)$ 中不稠密,因此 $W^{k,p}(\Omega)$ 的对偶空间不能作为广义函数的子空间嵌入.
**问题三:例1.11的证明** 
在 $R^n$ 中, $\delta$ 函数的傅里叶变换是1,在极坐标下,可以看出 $\delta\in H^{-s}$ 仅仅对于 $s>2/n$ .因此当 $n\geq2$ 时, $\delta\notin H^{-1}$
**问题四:证明** 
$$W^{n,1}(\Omega) 可以嵌入到 L^{\infty}(\Omega)~~~~~~~~but ~~~W^{1,n}(\Omega)不能嵌入到 L^{\infty}(\Omega)$$
**问题五:证明
$$||\widehat{D^{\alpha}v}||_{0,R^n}\leq ||\widehat {\bigtriangleup v}||_{0,R^n}$$**
