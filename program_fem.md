# 有限元程序


有限元程序这部分内容主要说了以下几方面：
 1. 网格数据结构
 再这部分中，主要说了节点（node）和单元（elem）。
（1）节点，也就是该点的位置，几何意义下表示坐标；单元是由顶点的编号组成，对于拓扑而言的。节点总数用 $$N$$ 来表示，单元总数用 $$NT$$ 来表示。 
（2）$d$ 维时，$node(1:N,1:d)$表示生成 $$N$$ 行 $d$ 列的矩阵；$elem(1:NT,1:d+1)$表示生成 $NT$ 行 $d+1$ 列的矩阵；注意：只有在三角化的情况下才是 $d+1$。
（3）$node(elem(:,2))-node(elem(:,1))$表示两个顶点相减
（4）编号方向：二维是按逆时针方向；三维是按右手法则（为了使面积或体积的符号为正）。
 2. 边界条件
 （1）**0**  没有边界，也称内边
 （2）**1**  狄利克雷边界（$u|_{\partial{\Omega}}=g$）
 （3）**2**  Neumann边界（$\frac{\partial u}{\partial {\vec n}}=g$ 或者$\nabla u\vec n=g$）
 （4）**3**  Robin边界（$\frac{\partial u}{\partial {\vec n}}+\vec n=g$）
其中，条件（1）（2）的变分形式不会改变。
 3. 几个代码问题：
（1）$bdFlag(1:NT,1:d+1)$表示生成 $NT$ 行 $d+1$ 列的矩阵,且里边的元素只有$0,1,2,3$,$d+1$ 在一维情况下表示条件对应的点，$d+1$ 在二维情况下表示条件对应的边，$d+1$ 在三维情况下表示条件对应的面。
（2）$totalbdFlag$二维下存储所有的边
（3）$bdFlag(:)==1$,表示把矩阵中所有为$1$的元素输出为$1$，其余输出为$0$
（4）$totalEdge(bdFlag(:)==1,:)$表示把矩阵变成1列，即（如文中例中6个单元，则变为18乘1的矩阵）为$1$的元素输出为$1$，其余输出为$0$，取出等于1时对应的$totalbdFlag$矩阵中的那一行
 4. 稀疏矩阵
 稀疏矩阵避免了在0处的操作,所以计算时间会比较少;并且稀疏矩阵的数据结构由于在0处不储存,所以储存记忆比较少.
格式:$COO$ 格式;$CSR$ 格式(按行压缩);$CSC$ 格式(按列压缩)
(1)$COO$ 格式:一个三元数组,行,列,非零元
s为表示非零元组成的向量;j为每个非零元的列指标;i为每个非零元的行指标
(2)$CSC$ 格式(按列压缩)
s为表示非零元组成的向量;j为每一列第一个不为0的元素在s中的位置(最后一个元素是nnz,即非零元的个数加1);i表示每一个非零元所在行数;
 5. 组装刚度矩阵$S(j(k):j(k+1)-1)$表示第k列的非零元素
例:对于矩阵
\begin{pmatrix}
1 & 0 & 0\\
0 & 2 & 4\\
0 & 0 & 0\\
0 & 9 & 0
\end{pmatrix}
$\vec i=(1,2,4,2)'$
$\vec j=(1,2,4,5)'$
$\vec s=(1,2,9,4)'$
$S(j(1):j(1+1)-1)=S(1:1)=1$
$S(j(2):j(2+1)-1)=S(2:3)=(2,9)'$
$S(j(3):j(3+1)-1)=S(4:4)=4$
 6. 组装刚度矩阵
 由
$$a(u,v)=(f,v)$$

且 $u=\sum_{i=1}^{N}v_i\phi_i$ ,取 $v=\phi_i$ ,则有
$$a(\sum_{i=1}^{N}v_i\phi_i,\phi_i)=(f,\phi_i)$$

即
$$\sum_{i=1}^{N}v_ia(\phi_i,\phi_i)=(f,\phi_i)$$

$a(\phi_i,\phi_i)$ 就是 $A=(a_{ij})$, 
$$a_{ij}=\int_{\Omega}\nabla {\phi_i}\nabla {\phi_j}\mathrm{d}x\\
=\sum_{\tau\in T}\int_{\tau}\nabla {\phi_i}\nabla {\phi_j}\mathrm{d}x$$

求出 $Ax=b$ 
这里 $A$ 是 $N\times N$ 矩阵; $\vec b=(f,\phi_i),i=1,2,\dots,N$ 
 7. 一些等式的过程
(1)  二维仿射变换:
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

 - 列表项

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
由于
$$F(\widehat{x})=B^{t}(\widehat{x})+C$$

这里
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
(2)证明:$\widehat{\nabla}\widehat{u}=B\nabla{u}$
证:
$$
\widehat{\nabla}\widehat{u}=
\begin{pmatrix}
\frac{\partial  \widehat{u}}{\partial  \widehat{x}}  \\
\frac{\partial  \widehat{u}}{\partial  \widehat{y}}
\end{pmatrix}\\
=\begin{pmatrix}
\frac{\partial  \widehat{u}}{\partial{x}}\frac{\partial x}{\partial  \widehat{x}} + \frac{\partial  \widehat{u}}{\partial{y}}\frac{\partial y}{\partial  \widehat{x}}\\
\frac{\partial  \widehat{u}}{\partial{x}}\frac{\partial x}{\partial  \widehat{y}} + \frac{\partial  \widehat{u}}{\partial{y}}\frac{\partial y}{\partial  \widehat{y}}\\
\end{pmatrix}\\
=\begin{pmatrix}
\frac{\partial{u}}{\partial  \widehat{x}} & \frac{\partial{y}}{\partial  \widehat{x}}\\
\frac{\partial{x}}{\partial  \widehat{y}} &\frac{\partial{y}}{\partial  \widehat{y}}
\end{pmatrix}
\begin{pmatrix}
\frac{\partial  \widehat{u}}{\partial{x}}  \\
\frac{\partial  \widehat{u}}{\partial{y}}
\end{pmatrix}\\
=B\nabla{u}
$$

所以
$$
\int_{\tau}\nabla{\lambda_i}\nabla{\lambda_j}\mathrm{d}x\mathrm{d}y\\
=\int_{\widehat{\tau}}(B^{-1}\widehat{\nabla}\widehat{\lambda_i})(B^{-1}\widehat{\nabla}\widehat{\lambda_j})\mathrm{d}\widehat{x}\mathrm{d}\widehat{y}\\
=\frac{1}{2}|det(B)|(B^{-1}\widehat{\nabla}\widehat{\lambda_i})(B^{-1}\widehat{\nabla}\widehat{\lambda_j})
$$
(3)证明:由$|\tau|=\frac{1}{d}|F_i|h_i$得
$$\nabla\lambda_i=\frac{1}{d!|\tau|}\vec n_i$$
从而
$$a_{ij}^{t}=\int_{\tau}\nabla {\phi_i}\nabla {\phi_j}\mathrm{d}x\\
=\frac{1}{d!^2|\tau|}\vec n_i\vec n_j$$
证明:考虑三维情形:由于 $\lambda_i$ 的方向导数为
$$\nabla \lambda_i\vec e=\frac{\lambda(x_i)-0}{h}=\frac{1}{h}$$
$\lambda_i(x)=\frac{\tau(x)}{|\tau|}$
且由$|\tau|=\frac{1}{d}|F_i|h_i$得
$$\frac{1}{h_i}=\frac{|F_i|}{d|\tau|}$$
所以$$\nabla \lambda_i\vec e=\frac{\lambda(x_i)-0}{h}=\frac{1}{h}=\frac{|F_i|}{3|\tau|}$$
由 $\vec n_i=\vec v_1\times\vec v_2$得
$$|\vec n_i|=2|F_i|$$
所以$$\nabla \lambda_i=\frac{|F_i|}{3|\tau|}\frac{\tau}{2|F_i|}=\frac{1}{6|\tau|}\vec n_i$$

$$a_{ij}^{t}=\int_{\tau}\nabla {\phi_i}\nabla {\phi_j}\mathrm{d}x\\
=\frac{1}{6|\tau|}\vec n_i\frac{1}{6|\tau|}\vec n_j\int_{\tau}\mathrm{d}x\\
=\frac{1}{36|\tau|}\vec n_i\vec n_j$$
 
- 一些代码的命令

```
ve(:,:,3)=node(elem(:,2),:)-node(elem(:,1),:);%表示所有单元的第三条边

node(elem(:,2),:) %所有单元的第二个顶点编号的坐标

area=0.5*abs(-ve(:,1,3).*ve(:,2,2)+ve(:,2,3).*ve(:,1,2));%面积
其中ve(:,i,j)中1表示x方向,2表示y方向;ve(:,1,3)表示x_2-x_1;ve(:,2,2)表示y_3-y_1

v12=node(face(:,2),:)-node(face(:,1),:)%所有单元的每个面的第二个顶点坐标减去第一个顶点坐标

allNormal=cross(v12,v13,2);%法向量,v12与v13的叉乘,2表示2维

mid1=(node(elem(:,2),:)-node(elem(:,3),:))/2;%中点坐标

bt1=area.*(f(mid2)+f(mid3))/6;
bt1=\int_{\tau}f\phi\mathrm{d}x=|\tau|w_i\sum_{k=1}^{3}f(midk)phi_1(midk)=|\tau|/3(f(mid1)0+f(mid2)/2+f(mid3)/2),由对称性可取w_i=1/3

bdNode=find(isBdNode);找出狄利克雷边的顶点编号

repmat(A,m,n)%m乘n矩阵,所有元素为A
```

 - 数值求积
 m阶积分精度:常数到m阶多项式的积分是精确成立的.
(1)在$p_i$点处通过函数的加权平均求近似积分:

$$\int_{\tau}f(x)\mathrm{d}x\approx I_n(f):=\sum_{i=1}^{n}f(p_i)w_i|\tau|$$

(2)一点公式:
$$I_1(f)=f(c_{\tau})|\tau|,c_{\tau}=\frac{1}{d+1}\sum_{i=1}^{d+1}x_i$$

(3)梯形公式:
$$I_1(f)=\frac{1}{d+1}\sum_{i=1}^{d+1}f(x_i)|\tau|$$

(4)Simpson公式:
$$\int_{a}^{b}f(x)\mathrm{d}x\approx(b-a)\frac{1}{6}(f(a)+4f((a+b)/2)+f(b))$$

(5)取三边中点 $m_i,i=1,2,3$:
$$int_{\tau}f(x)\mathrm{d}x\approx|\tau|\frac{1}{3}\sum_{i=1}^{3}f(m_i)$$
