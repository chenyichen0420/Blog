### 生成函数

一些前置概念，在后面多个板块会用到。

积性函数：满足 $f(ab)=f(a)\times f(b)(\gcd(a,b)=1)$。

那么，知道因式分解时有：

$f(p_1^{c_1}\times p_2^{c_2}\times\dots)=f(p_1^{c_1})\times f(p_2^{c_2})\times\dots$。

常见积性函数：

$\sigma_n$：$n$ 的因子数。

$\mu_n$：莫比乌斯函数。

$\varphi_n$：欧拉函数

$d_n$：$n$ 的约数个数。

$e_n$：$[n=1]$。

$I_n=1$。（常见写为 $1_n$）。

$id_n=n$。（常见写为 $I,Id$）。

#### 普通生成函数

对于数列 $A_i(i\in[0,n])$，其 OGF 为 $A(x)=\Sigma_{i=0}^nA_ix^i$。

看起来不知道有什么用，给个例题：有三种物品，每种物品分别有 $3,2,3$ 个，问从这三种物品里面拿出 $4$ 个的方案数有多少种？

假设 $f(i,j)$：转移到物品 $i$，已经选了 $j$ 个。

能不能更方便一些？

对每一个数生成出其生成函数($A1_i=A3_i=1,i\in[0,3],A2_i=1,i\in[0,2]$)，即 $A1(x)=A3(x)=1+x+x^2+x^3$，$A2(x)=1+x+x^2$。令 $F(x)=A1(x)A2(x)A3(x)$，则答案为 $[x^4]F(x)$，即 $x^4$ 的系数。

其实生成函数的系数之间的乘法对应了你手数时每一项选择的过程。

需要注意的是，这些生成函数往往可能会涉及到无穷的累加。请别忘了我们还有展开式，无穷序列加起来可能会变成之前的分式。

典型手算例题有[《干饭》](https://www.luogu.com.cn/problem/P10780)和[《末日时在干什么》](https://www.luogu.com.cn/problem/P2000)。（不正经.jbg）

其实我们不难看出，绝大多数的情况下，$A$ 数组都只会涉及到 $0,1$ 两种值，来表示可不可取。拆解的时候多使用换元法，因式分解法，往往会有奇效。

补充一个公式：$\Sigma_{i=0}^kx^k=\frac{1-x^{k+1}}{1-x}$。

#### 指数生成函数

对于数列 $A_i(i\in[0,n])$，其 EGF 为 $A(x)=\Sigma_{i=0}^nA_i\frac{x^i}{i!}$。

对于大部分带标号的问题，可能会有类似的形式：$f(i)f(j)(_i^{i+j})=f(i+j)$。一个典型的例子就是多重集的排列。

有 $f(i)f(j)\frac{(i+j)!}{i!j!}=f(i+j)$，即 $\frac{f(i)}{i!}\times\frac{f(j)}{j!}=\frac{f(i+j)}{(i+j)!}$。

因此这么定义。这里较为常用的公式是关于 $e$ 的泰勒展开。

有一个公式需要记一下：

$\Sigma_{i=0}^{ \inf}\frac{x^{2i}}{(2i)!}=\frac{e^x+e^{-x}}{2}$。证明显然，展开后就是了。

#### 狄利克雷生成函数

对于**无穷**数列 $A_i(i\in[1,\infin))$，其 DGF 为 $A(x)=\Sigma_{i=1}^n\frac{A_i}{i^x}$。

如果 $A$ 满足积性，那么其 DGF 也可以由质数幂处的取值表示为 $A(x)=\prod_{p\in \mathbb{P}}(1+\frac{f_p}{p^x}+\frac{f_{p^2}}{p^{2x}}+\frac{f_{p^3}}{p^{3x}}+\dots)$。

有一些常见的 DGF，可以记一下。

黎曼函数 $\zeta$ 可用序列定义为 $[1,1,1,1,\dots]$，另一种形式为 $\zeta(x)=\prod_{p\in \mathbb{P}}\frac{1}{1-p^{-x}}$。

莫比乌斯函数的 DGF 定义为 $\tilde{M}(x)=\prod_{p\in \mathbb{P}}(1-p^{-x})$。也就是说，$\zeta(x)\tilde{M}(x)=1$。

欧拉函数的 DGF 定义为 $\tilde{\Phi}(x)=\prod_{p\in \mathbb{P}}\frac{1-p^{-x}}{1-p^{1-x}}$。也就是说 $\tilde{\Phi}(x)\zeta(x)=\zeta(x-1)$。

### 狄利克雷卷积

若 $f=h\times g$，则令 $f(x)=\Sigma_{d|x}h(d)\times g(x/d)$。

$f,g$ 积性，则 $f\times g$ 积性。

$f\times e=f$

$\varphi\times I=id$

$\mu\times I=e$

若 $f\times g=e$，则称 $f,g$ 互逆。

可以做到 $O(n\log\log n)$ 求 $g=f\times I$ 或 $g=f\times\mu$。

对于其余的卷积，其复杂度一般为 $O(n\ln n)$，调和级数。

### 莫比乌斯反演

本质：$\mu\times I=e$。

证明：$\Sigma_{d|n}\mu_d=\Sigma_iC_{\omega_n}^i(-1)^i=(1-1)^{\omega_n}=[n=1]$。

其中的 $\omega_n$ 指 $n$ 的质因子个数。

$f=g\times I$，$f(n)=\Sigma_{d|n}g(d)$。

则有 $g=f\times\mu$，$g(n)=\Sigma_{d|n}f(d)\mu(n/d)$。显然，函数的逆放到这里一定成立。

主要应用就是拆 $\gcd$。套路就是去枚举 $\gcd$ 的值，然后对取等条件作卷积。

最常用的场景就是 $[p=1]=\Sigma_{d|p}\mu(d)$，尤其是 $[\gcd(a,b)=1]$ 的形式。

一种较为常见的形式是求 $\sum_{i=1}^n\sum_{j=1}^m f(\gcd(i,j))$。这时候我们构造函数 $g$，满足 $f(x)=g*I=\sum_{d|x}g(d)$。原式转化为 $\sum_{i=1}^n\sum_{j=1}^m\sum_{d|gcd(i,j)}g(d)=\sum_{d=1}g(d)\lfloor\frac{n}{d}\rfloor\lfloor\frac{m}{d}\rfloor$。
