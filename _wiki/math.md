---
layout: wiki
title: 机器学习的数学基础
categories: Mathematics
description: 机器学习的数学基础
keywords: 机器学习, 数学基础
---

-----
**目录**

* TOC
{:toc}
-----

### 高等数学

<p><strong>1.导数定义：</strong></p>
<p>导数和微分的概念</p>
<p>$f'({x_{0}})=\underset{\Delta x\to 0}{\mathop{\lim }}\,\frac{f({x_{0}}+\Delta x)-f({x_{0}})}{\Delta x}$    （1）</p>
<p>或者：</p>
<p>$f'({x_{0}})=\underset{x\to {x_{0}}}{\mathop{\lim }}\,\frac{f(x)-f({x_{0}})}{x-{x_{0}}}$           （2）</p>
<p><strong>2.左右导数导数的几何意义和物理意义</strong></p>
<p>函数$f(x)$在$x_0$处的左、右导数分别定义为：</p>
<p>左导数：${f'_{-}}({x_{0}})=\underset{\Delta x\to {0^{-}}}{\mathop{\lim }}\,\frac{f({x_{0}}+\Delta x)-f({x_{0}})}{\Delta x}=\underset{x\to x_{0}^{-}}{\mathop{\lim }}\,\frac{f(x)-f({x_{0}})}{x-{x_{0}}},(x={x_{0}}+\Delta x)$</p>
<p>右导数：${f'_{+}}({x_{0}})=\underset{\Delta x\to {0^{+}}}{\mathop{\lim }}\,\frac{f({x_{0}}+\Delta x)-f({x_{0}})}{\Delta x}=\underset{x\to x_{0}^{+}}{\mathop{\lim }}\,\frac{f(x)-f({x_{0}})}{x-{x_{0}}}$</p>
<p><strong>3.函数的可导性与连续性之间的关系</strong></p>
<p><strong>Th1:</strong> 函数$f(x)$在$x_0$处可微$\Leftrightarrow f(x)$在$x_0$处可导</p>
<p><strong>Th2:</strong> 若函数在点$x_0$处可导，则$y=f(x)$在点$x_0$处连续，反之则不成立。即函数连续不一定可导。</p>
<p><strong>Th3:</strong> ${f}'({x_{0}})$存在$\Leftrightarrow {f'_{-}}({x_{0}})={f'_{+}}({x_{0}})$</p>
<p><strong>4.平面曲线的切线和法线</strong></p>
<p>切线方程 : $y-{y_{0}}=f'({x_{0}})(x-{x_{0}})$
法线方程：$y-{y_{0}}=-\frac{1}{f'({x_{0}})}(x-{x_{0}}),f'({x_{0}})\ne 0$</p>
<p><strong>5.四则运算法则</strong>
设函数$u=u(x)，v=v(x)$]在点$x$可导则
(1) $(u\pm v{)}'={u}'\pm {v}'$       $d(u\pm v)=du\pm dv$
(2) $(uv{)}'=u{v}'+v{u}'$        $d(uv)=udv+vdu$
(3) $(\frac{u}{v}{)}'=\frac{v{u}'-u{v}'}{v^{2}}(v\ne 0)$       $d(\frac{u}{v})=\frac{vdu-udv}{v^{2}}​$</p>
<p><strong>6.基本导数与微分表</strong>
(1) $y=c$（常数）       ${y}'=0$          $dy=0$
(2) $y={x^{\alpha }}$($\alpha $为实数)    ${y}'=\alpha {x^{\alpha -1}}$      $dy=\alpha {x^{\alpha -1}}dx$
(3) $y={a^{x}}$      ${y}'={a^{x}}\ln a$         $dy={a^{x}}\ln adx$
  特例:   $({e^{x}}{)}'={e^{x}}$             $d({e^{x}})={e^{x}}dx$</p>
<p>(4) ${y}'=\frac{1}{x\ln a}$           </p>
<p>$dy=\frac{1}{x\ln a}dx$
  特例:$y=\ln x$                      $(\ln x{)}'=\frac{1}{x}$       $d(\ln x)=\frac{1}{x}dx$</p>
<p>(5) $y=\sin x$         </p>
<p>${y}'=\cos x$        $d(\sin x)=\cos xdx$</p>
<p>(6) $y=\cos x$      </p>
<p>${y}'=-\sin x$       $d(\cos x)=-\sin xdx$</p>
<p>(7) $y=\tan x$  </p>
<p>${y}'=\frac{1}{\cos ^{2}x}={\sec ^{2}}x$  $d(\tan x)={\sec ^{2}}xdx$
(8) $y=\cot x$ ${y}'=-\frac{1}{\sin ^{2}x}=-{\csc ^{2}}x$  $d(\cot x)=-{\csc ^{2}}xdx$
(9) $y=\sec x$ ${y}'=\sec x\tan x$     </p>
<p> $d(\sec x)=\sec x\tan xdx$
(10) $y=\csc x$ ${y}'=-\csc x\cot x$    </p>
<p>$d(\csc x)=-\csc x\cot xdx$
(11) $y=\arcsin x$  </p>
<p>${y}'=\frac{1}{\sqrt{1-{x^{2}}}}$   </p>
<p>$d(\arcsin x)=\frac{1}{\sqrt{1-{x^{2}}}}dx$
(12) $y=\arccos x$ </p>
<p>${y}'=-\frac{1}{\sqrt{1-{x^{2}}}}$     $d(\arccos x)=-\frac{1}{\sqrt{1-{x^{2}}}}dx$</p>
<p>(13) $y=\arctan x$ </p>
<p>${y}'=\frac{1}{1+{x^{2}}}$     $d(\arctan x)=\frac{1}{1+{x^{2}}}dx$</p>
<p>(14) $y=\operatorname{arc}\cot x$      </p>
<p>${y}'=-\frac{1}{1+{x^{2}}}$   </p>
<p>$d(\operatorname{arc}\cot x)=-\frac{1}{1+{x^{2}}}dx$
(15) $y=shx$    </p>
<p>${y}'=chx$       $d(shx)=chxdx$</p>
<p>(16) $y=chx$    </p>
<p>${y}'=shx$       $d(chx)=shxdx$</p>
<p><strong>7.复合函数，反函数，隐函数以及参数方程所确定的函数的微分法</strong></p>
<p>(1) 反函数的运算法则: 设$y=f(x)$在点$x$的某邻域内单调连续，在点$x$处可导且${f}'(x)\ne 0$，则其反函数在点$x$所对应的$y$处可导，并且有$\frac{dy}{dx}=\frac{1}{\frac{dx}{dy}}$
(2) 复合函数的运算法则:若$\mu =\varphi (x)$在点$x$可导,而$y=f(\mu )$在对应点$\mu $($\mu =\varphi (x)$)可导,则复合函数$y=f(\varphi (x))$在点$x$可导,且${y}'={f}'(\mu )\cdot {\varphi }'(x)$
(3) 隐函数导数$\frac{dy}{dx}$的求法一般有三种方法：
1)方程两边对$x$求导，要记住$y$是$x$的函数，则$y$的函数是$x$的复合函数.例如$\frac{1}{y}$，${y^{2}}$，$ln y$，${e^{y}}$等均是$x$的复合函数.
对$x$求导应按复合函数连锁法则做.
2)公式法.由$F(x,y)=0$知 $\frac{dy}{dx}=-\frac{f'_{x}(x,y)}{f'_{y}(x,y)}$,其中，${f'_{x}}(x,y)$，
${f'_{y}}(x,y)$分别表示$F(x,y)$对$x$和$y$的偏导数
3)利用微分形式不变性</p>
<p><strong>8.常用高阶导数公式</strong></p>
<p>（1）$({a^{x}}){\,^{(n)}}={a^{x}}{\ln ^{n}}a\quad (a>{0})\quad \quad ({e^{x}}){\,^{(n)}}={e}{\,^{x}}$
（2）$(\sin kx{)}{\,^{(n)}}={k^{n}}\sin (kx+n\cdot \frac{\pi }{2})$
（3）$(\cos kx{)}{\,^{(n)}}={k^{n}}\cos (kx+n\cdot \frac{\pi }{2})$
（4）$({x^{m}}){\,^{(n)}}=m(m-1)\cdots (m-n+1){x^{m-n}}$
（5）$(\ln x){\,^{(n)}}={(-{1})^{(n-{1})}}\frac{(n-{1})!}{x^{n}}$
（6）莱布尼兹公式：若$u(x)\,,v(x)$均$n$阶可导，则
 ${(uv)^{(n)}}=\sum\limits_{i={0}}^{n}{c_{n}^{i}{u^{(i)}}{v^{(n-i)}}}$，其中${u^{({0})}}=u$，${v^{({0})}}=v$</p>
<p><strong>9.微分中值定理，泰勒公式</strong></p>
<p><strong>Th1:</strong>(费马定理)</p>
<p>若函数$f(x)$满足条件：
(1)函数$f(x)$在${x_{0}}$的某邻域内有定义，并且在此邻域内恒有
$f(x)\le f({x_{0}})$或$f(x)\ge f({x_{0}})$,</p>
<p>(2) $f(x)$在${x_{0}}$处可导,则有 ${f}'({x_{0}})=0$</p>
<p><strong>Th2:</strong>(罗尔定理) </p>
<p>设函数$f(x)$满足条件：
(1)在闭区间$[a,b]$上连续；</p>
<p>(2)在$(a,b)$内可导；</p>
<p>(3)$f(a)=f(b)$；</p>
<p>则在$(a,b)$内一存在个$\xi $，使  ${f}'(\xi )=0$
<strong>Th3:</strong> (拉格朗日中值定理) </p>
<p>设函数$f(x)$满足条件：
(1)在$[a,b]$上连续；</p>
<p>(2)在$(a,b)$内可导；</p>
<p>则在$(a,b)$内一存在个$\xi $，使  $\frac{f(b)-f(a)}{b-a}={f}'(\xi )$</p>
<p><strong>Th4:</strong> (柯西中值定理)</p>
<p> 设函数$f(x)$，$g(x)$满足条件：
(1) 在$[a,b]$上连续；</p>
<p>(2) 在$(a,b)$内可导且${f}'(x)$，${g}'(x)$均存在，且${g}'(x)\ne 0$</p>
<p>则在$(a,b)$内存在一个$\xi $，使  $\frac{f(b)-f(a)}{g(b)-g(a)}=\frac{f'(\xi )}{g'(\xi )}$</p>
<p><strong>10.洛必达法则</strong>
法则Ⅰ ($\frac{0}{0}$型)
设函数$f\left( x \right),g\left( x \right)$满足条件：
 $\underset{x\to {x_{0}}}{\mathop{\lim }}\,f\left( x \right)=0,\underset{x\to {x_{0}}}{\mathop{\lim }}\,g\left( x \right)=0$; </p>
<p>$f\left( x \right),g\left( x \right)$在${x_{0}}$的邻域内可导，(在${x_{0}}$处可除外)且${g}'\left( x \right)\ne 0$;</p>
<p>$\underset{x\to {x_{0}}}{\mathop{\lim }}\,\frac{f'\left( x \right)}{g'\left( x \right)}$存在(或$\infty $)。</p>
<p>则:
$\underset{x\to {x_{0}}}{\mathop{\lim }}\,\frac{f\left( x \right)}{g\left( x \right)}=\underset{x\to {x_{0}}}{\mathop{\lim }}\,\frac{f'\left( x \right)}{g'\left( x \right)}$。
法则${I'}$ ($\frac{0}{0}$型)设函数$f\left( x \right),g\left( x \right)$满足条件：
$\underset{x\to \infty }{\mathop{\lim }}\,f\left( x \right)=0,\underset{x\to \infty }{\mathop{\lim }}\,g\left( x \right)=0$;</p>
<p>存在一个$X>0$,当$\left| x \right|>X$时,$f\left( x \right),g\left( x \right)$可导,且${g}'\left( x \right)\ne 0$;$\underset{x\to {x_{0}}}{\mathop{\lim }}\,\frac{f'\left( x \right)}{g'\left( x \right)}$存在(或$\infty $)。</p>
<p>则:
$\underset{x\to {x_{0}}}{\mathop{\lim }}\,\frac{f\left( x \right)}{g\left( x \right)}=\underset{x\to {x_{0}}}{\mathop{\lim }}\,\frac{f'\left( x \right)}{g'\left( x \right)}$
法则Ⅱ($\frac{\infty }{\infty }$型) 设函数$f\left( x \right),g\left( x \right)$满足条件：
$\underset{x\to {x_{0}}}{\mathop{\lim }}\,f\left( x \right)=\infty ,\underset{x\to {x_{0}}}{\mathop{\lim }}\,g\left( x \right)=\infty $;   $f\left( x \right),g\left( x \right)$在${x_{0}}$ 的邻域内可导(在${x_{0}}$处可除外)且${g}'\left( x \right)\ne 0$;$\underset{x\to {x_{0}}}{\mathop{\lim }}\,\frac{f'\left( x \right)}{g'\left( x \right)}$存在(或$\infty $)。则
$\underset{x\to {x_{0}}}{\mathop{\lim }}\,\frac{f\left( x \right)}{g\left( x \right)}=\underset{x\to {x_{0}}}{\mathop{\lim }}\,\frac{f'\left( x \right)}{g'\left( x \right)}.$同理法则${I{I}'}$($\frac{\infty }{\infty }$型)仿法则${I'}$可写出。</p>
<p><strong>11.泰勒公式</strong></p>
<p>设函数$f(x)$在点${x_{0}}$处的某邻域内具有$n+1$阶导数，则对该邻域内异于${x_{0}}$的任意点$x$，在${x_{0}}$与$x$之间至少存在
一个$\xi $，使得：
$f(x)=f({x_{0}})+{f}'({x_{0}})(x-{x_{0}})+\frac{1}{2!}{f}''({x_{0}}){(x-{x_{0}})^{2}}+\cdots $ 
$+\frac{f^{(n)}({x_{0}})}{n!}{(x-{x_{0}})^{n}}+{R_{n}}(x)$
 其中 ${R_{n}}(x)=\frac{f^{(n+1)}(\xi )}{(n+1)!}{(x-{x_{0}})^{n+1}}$称为$f(x)$在点${x_{0}}$处的$n$阶泰勒余项。</p>
<p>令${x_{0}}=0$，则$n$阶泰勒公式
$f(x)=f(0)+{f}'(0)x+\frac{1}{2!}{f}''(0){x^{2}}+\cdots +\frac{f^{(n)}(0)}{n!}{x^{n}}+{R_{n}}(x)$……(1)
其中 ${R_{n}}(x)=\frac{f^{(n+1)}(\xi )}{(n+1)!}{x^{n+1}}$，$\xi $在0与$x$之间.(1)式称为麦克劳林公式</p>
<p><strong>常用五种函数在${x_{0}}=0$处的泰勒公式</strong></p>
<p>(1) ${e^{x}}=1+x+\frac{1}{2!}{x^{2}}+\cdots +\frac{1}{n!}{x^{n}}+\frac{x^{n+1}}{(n+1)!}{e^{\xi }}$ </p>
<p>或 $=1+x+\frac{1}{2!}{x^{2}}+\cdots +\frac{1}{n!}{x^{n}}+o({x^{n}})$</p>
<p>(2) $\sin x=x-\frac{1}{3!}{x^{3}}+\cdots +\frac{x^{n}}{n!}\sin \frac{n\pi }{2}+\frac{x^{n+1}}{(n+1)!}\sin (\xi +\frac{n+1}{2}\pi )$</p>
<p>或  $=x-\frac{1}{3!}{x^{3}}+\cdots +\frac{x^{n}}{n!}\sin \frac{n\pi }{2}+o({x^{n}})$</p>
<p>(3) $\cos x=1-\frac{1}{2!}{x^{2}}+\cdots +\frac{x^{n}}{n!}\cos \frac{n\pi }{2}+\frac{x^{n+1}}{(n+1)!}\cos (\xi +\frac{n+1}{2}\pi )$</p>
<p>或   $=1-\frac{1}{2!}{x^{2}}+\cdots +\frac{x^{n}}{n!}\cos \frac{n\pi }{2}+o({x^{n}})$</p>
<p>(4) $\ln (1+x)=x-\frac{1}{2}{x^{2}}+\frac{1}{3}{x^{3}}-\cdots +{(-1)^{n-1}}\frac{x^{n}}{n}+\frac{(-1)^{n}{x^{n+1}}}{(n+1){(1+\xi )^{n+1}}}$</p>
<p>或      $=x-\frac{1}{2}{x^{2}}+\frac{1}{3}{x^{3}}-\cdots +{(-1)^{n-1}}\frac{x^{n}}{n}+o({x^{n}})$</p>
<p>(5) ${(1+x)^{m}}=1+mx+\frac{m(m-1)}{2!}{x^{2}}+\cdots +\frac{m(m-1)\cdots (m-n+1)}{n!}{x^{n}}$ 
$+\frac{m(m-1)\cdots (m-n+1)}{(n+1)!}{x^{n+1}}{(1+\xi )^{m-n-1}}$ </p>
<p>或 ${(1+x)^{m}}=1+mx+\frac{m(m-1)}{2!}{x^{2}}+\cdots $ $+\frac{m(m-1)\cdots (m-n+1)}{n!}{x^{n}}+o({x^{n}})$</p>
<p><strong>12.函数单调性的判断</strong>
<strong>Th1:</strong>  设函数$f(x)$在$(a,b)$区间内可导，如果对$\forall x\in (a,b)$，都有$f\,'(x)>0$（或$f\,'(x)<0$），则函数$f(x)$在$(a,b)$内是单调增加的（或单调减少）</p>
<p><strong>Th2:</strong> （取极值的必要条件）设函数$f(x)$在${x_{0}}$处可导，且在${x_{0}}$处取极值，则$f\,'({x_{0}})=0$。</p>
<p><strong>Th3:</strong> （取极值的第一充分条件）设函数$f(x)$在${x_{0}}$的某一邻域内可微，且$f\,'({x_{0}})=0$（或$f(x)$在${x_{0}}$处连续，但$f\,'({x_{0}})$不存在。）
(1)若当$x$经过${x_{0}}$时，$f\,'(x)$由“+”变“-”，则$f({x_{0}})$为极大值；
(2)若当$x​$经过${x_{0}}​$时，$f\,'(x)$由“-”变“+”，则$f({x_{0}})$为极小值；
(3)若$f\,'(x)$经过$x={x_{0}}$的两侧不变号，则$f({x_{0}})$不是极值。</p>
<p><strong>Th4:</strong> (取极值的第二充分条件)设$f(x)$在点${x_{0}}$处有$f''(x)\ne 0$，且$f\,'({x_{0}})=0$，则 当$f'\,'({x_{0}})<0$时，$f({x_{0}})$为极大值；
当$f'\,'({x_{0}})>0$时，$f({x_{0}})$为极小值。
注：如果$f'\,'({x_{0}})<0$，此方法失效。</p>
<p><strong>13.渐近线的求法</strong>
(1)水平渐近线   若$\underset{x\to +\infty }{\mathop{\lim }}\,f(x)=b$，或$\underset{x\to -\infty }{\mathop{\lim }}\,f(x)=b$，则</p>
<p>$y=b$称为函数$y=f(x)$的水平渐近线。</p>
<p>(2)铅直渐近线   若$\underset{x\to x_{0}^{-}}{\mathop{\lim }}\,f(x)=\infty $，或$\underset{x\to x_{0}^{+}}{\mathop{\lim }}\,f(x)=\infty $，则</p>
<p>$x={x_{0}}$称为$y=f(x)$的铅直渐近线。</p>
<p>(3)斜渐近线   若$a=\underset{x\to \infty }{\mathop{\lim }}\,\frac{f(x)}{x},\quad b=\underset{x\to \infty }{\mathop{\lim }}\,[f(x)-ax]$，则
$y=ax+b$称为$y=f(x)$的斜渐近线。</p>
<p><strong>14.函数凹凸性的判断</strong>
<strong>Th1:</strong> (凹凸性的判别定理）若在I上$f''(x)<0$（或$f''(x)>0$），则$f(x)$在I上是凸的（或凹的）。</p>
<p><strong>Th2:</strong> (拐点的判别定理1)若在${x_{0}}$处$f''(x)=0$，（或$f''(x)$不存在），当$x$变动经过${x_{0}}$时，$f''(x)$变号，则$({x_{0}},f({x_{0}}))$为拐点。</p>
<p><strong>Th3:</strong> (拐点的判别定理2)设$f(x)$在${x_{0}}$点的某邻域内有三阶导数，且$f''(x)=0$，$f'''(x)\ne 0$，则$({x_{0}},f({x_{0}}))$为拐点。</p>
<p><strong>15.弧微分</strong></p>
<p>$dS=\sqrt{1+y{'^{2}}}dx$</p>
<p><strong>16.曲率</strong></p>
<p>曲线$y=f(x)$在点$(x,y)$处的曲率$k=\frac{\left| y'' \right|}{(1+y{'^{2}})^{\tfrac{3}{2}}}$。
对于参数方程$\left\{\begin{matrix} x=\varphi (t) \\ y=\psi (t) \end{matrix}\right.$，$k=\frac{\left| \varphi '(t)\psi ''(t)-\varphi ''(t)\psi '(t) \right|}{[\varphi {'^{2}}(t)+\psi {'^{2}}(t)]^{\tfrac{3}{2}}}$。</p>
<p><strong>17.曲率半径</strong></p>
<p>曲线在点$M$处的曲率$k(k\ne 0)$与曲线在点$M$处的曲率半径$\rho $有如下关系：$\rho =\frac{1}{k}$。</p>

### 线性代数

#### 行列式

<p><strong>1.行列式按行（列）展开定理</strong></p>
<p>(1) 设$A = ( a_{ij} )_{n \times n}$，则：$a_{i1}A_{j1} +a_{i2}A_{j2} + \cdots + a_{in}A_{jn} = \begin{cases}|A|,i=j\\ 0,i \neq j\end{cases}$</p>
<p>或$a_{1i}A_{1j} + a_{2i}A_{2j} + \cdots + a_{ni}A_{nj} = \begin{cases}|A|,i=j\\ 0,i \neq j\end{cases}$即 $AA^{*} = A^{*}A = \left| A \right|E,$其中：$A^{*} = \begin{pmatrix} A_{11} & A_{12} & \ldots & A_{1n} \\ A_{21} & A_{22} & \ldots & A_{2n} \\ \ldots & \ldots & \ldots & \ldots \\ A_{n1} & A_{n2} & \ldots & A_{nn} \\ \end{pmatrix} = (A_{ji}) = {(A_{ij})}^{T}$</p>
<p>$D_{n} = \begin{vmatrix} 1 & 1 & \ldots & 1 \\ x_{1} & x_{2} & \ldots & x_{n} \\ \ldots & \ldots & \ldots & \ldots \\ x_{1}^{n - 1} & x_{2}^{n - 1} & \ldots & x_{n}^{n - 1} \\ \end{vmatrix} = \prod_{1 \leq j < i \leq n}^{}\,(x_{i} - x_{j})$</p>
<p>(2) 设$A,B$为$n$阶方阵，则$\left| {AB} \right| = \left| A \right|\left| B \right| = \left| B \right|\left| A \right| = \left| {BA} \right|$，但$\left| A \pm B \right| = \left| A \right| \pm \left| B \right|$不一定成立。</p>
<p>(3) $\left| {kA} \right| = k^{n}\left| A \right|$,$A$为$n$阶方阵。</p>
<p>(4) 设$A$为$n$阶方阵，$|A^{T}| = |A|;|A^{- 1}| = |A|^{- 1}$（若$A$可逆），$|A^{*}| = |A|^{n - 1}$</p>
<p>$n \geq 2$</p>
<p>(5) $\left| \begin{matrix}  & {A\quad O} \\  & {O\quad B} \\ \end{matrix} \right| = \left| \begin{matrix}  & {A\quad C} \\  & {O\quad B} \\ \end{matrix} \right| = \left| \begin{matrix}  & {A\quad O} \\  & {C\quad B} \\ \end{matrix} \right| =| A||B|$
，$A,B$为方阵，但$\left| \begin{matrix} {O} & A_{m \times m} \\  B_{n \times n} & { O} \\ \end{matrix} \right| = ({- 1)}^{mn}|A||B|$ 。</p>
<p>(6) 范德蒙行列式$D_{n} = \begin{vmatrix} 1 & 1 & \ldots & 1 \\ x_{1} & x_{2} & \ldots & x_{n} \\ \ldots & \ldots & \ldots & \ldots \\ x_{1}^{n - 1} & x_{2}^{n 1} & \ldots & x_{n}^{n - 1} \\ \end{vmatrix} =  \prod_{1 \leq j < i \leq n}^{}\,(x_{i} - x_{j})$</p>
<p>设$A$是$n$阶方阵，$\lambda_{i}(i = 1,2\cdots,n)$是$A$的$n$个特征值，则
$|A| = \prod_{i = 1}^{n}\lambda_{i}​$</p>

#### 矩阵

<p>矩阵：$m \times n$个数$a_{ij}$排成$m$行$n$列的表格$\begin{bmatrix}  a_{11}\quad a_{12}\quad\cdots\quad a_{1n} \\ a_{21}\quad a_{22}\quad\cdots\quad a_{2n} \\ \quad\cdots\cdots\cdots\cdots\cdots \\  a_{m1}\quad a_{m2}\quad\cdots\quad a_{mn} \\ \end{bmatrix}$ 称为矩阵，简记为$A$，或者$\left( a_{ij} \right)_{m \times n}$ 。若$m = n$，则称$A$是$n$阶矩阵或$n$阶方阵。</p>
<p><strong>矩阵的线性运算</strong></p>
<p><strong>1.矩阵的加法</strong></p>
<p>设$A = (a_{ij}),B = (b_{ij})$是两个$m \times n$矩阵，则$m \times n$ 矩阵$C = c_{ij}) = a_{ij} + b_{ij}$称为矩阵$A$与$B$的和，记为$A + B = C$ 。</p>
<p><strong>2.矩阵的数乘</strong></p>
<p>设$A = (a_{ij})$是$m \times n$矩阵，$k$是一个常数，则$m \times n$矩阵$(ka_{ij})$称为数$k$与矩阵$A$的数乘，记为${kA}$。</p>
<p><strong>3.矩阵的乘法</strong></p>
<p>设$A = (a_{ij})$是$m \times n$矩阵，$B = (b_{ij})$是$n \times s$矩阵，那么$m \times s$矩阵$C = (c_{ij})$，其中$c_{ij} = a_{i1}b_{1j} + a_{i2}b_{2j} + \cdots + a_{in}b_{nj} = \sum_{k =1}^{n}{a_{ik}b_{kj}}$称为${AB}$的乘积，记为$C = AB$ 。</p>
<p><strong>4.</strong> $\mathbf{A}^{\mathbf{T}}$<strong>、</strong>$\mathbf{A}^{\mathbf{-1}}$<strong>、</strong>$\mathbf{A}^{\mathbf{*}}$<strong>三者之间的关系</strong></p>
<p>(1) ${(A^{T})}^{T} = A,{(AB)}^{T} = B^{T}A^{T},{(kA)}^{T} = kA^{T},{(A \pm B)}^{T} = A^{T} \pm B^{T}$</p>
<p>(2) $\left( A^{- 1} \right)^{- 1} = A,\left( {AB} \right)^{- 1} = B^{- 1}A^{- 1},\left( {kA} \right)^{- 1} = \frac{1}{k}A^{- 1},$</p>
<p>但 ${(A \pm B)}^{- 1} = A^{- 1} \pm B^{- 1}$不一定成立。</p>
<p>(3) $\left( A^{*} \right)^{*} = |A|^{n - 2}\ A\ \ (n \geq 3)$，$\left({AB} \right)^{*} = B^{*}A^{*},$ $\left( {kA} \right)^{*} = k^{n -1}A^{*}{\ \ }\left( n \geq 2 \right)$</p>
<p>但$\left( A \pm B \right)^{*} = A^{*} \pm B^{*}$不一定成立。</p>
<p>(4) ${(A^{- 1})}^{T} = {(A^{T})}^{- 1},\ \left( A^{- 1} \right)^{*} ={(AA^{*})}^{- 1},{(A^{*})}^{T} = \left( A^{T} \right)^{*}$</p>
<p><strong>5.有关</strong>$\mathbf{A}^{\mathbf{*}}$<strong>的结论</strong></p>
<p>(1) $AA^{*} = A^{*}A = |A|E$</p>
<p>(2) $|A^{*}| = |A|^{n - 1}\ (n \geq 2),\ \ \ \ {(kA)}^{*} = k^{n -1}A^{*},{\ \ \left( A^{*} \right)}^{*} = |A|^{n - 2}A(n \geq 3)$</p>
<p>(3) 若$A$可逆，则$A^{*} = |A|A^{- 1},{(A^{*})}^{*} = \frac{1}{|A|}A$</p>
<p>(4) 若$A​$为$n​$阶方阵，则：</p>
<p>$r(A^*)=\begin{cases}n,\quad r(A)=n\\ 1,\quad r(A)=n-1\\ 0,\quad r(A)<n-1\end{cases}$</p>
<p><strong>6.有关</strong>$\mathbf{A}^{\mathbf{- 1}}$<strong>的结论</strong></p>
<p>$A$可逆$\Leftrightarrow AB = E; \Leftrightarrow |A| \neq 0; \Leftrightarrow r(A) = n;$</p>
<p>$\Leftrightarrow A$可以表示为初等矩阵的乘积；$\Leftrightarrow A;\Leftrightarrow Ax = 0$。</p>
<p><strong>7.有关矩阵秩的结论</strong></p>
<p>(1) 秩$r(A)$=行秩=列秩；</p>
<p>(2) $r(A_{m \times n}) \leq \min(m,n);$</p>
<p>(3) $A \neq 0 \Rightarrow r(A) \geq 1$；</p>
<p>(4) $r(A \pm B) \leq r(A) + r(B);$</p>
<p>(5) 初等变换不改变矩阵的秩</p>
<p>(6) $r(A) + r(B) - n \leq r(AB) \leq \min(r(A),r(B)),$特别若$AB = O$
则：$r(A) + r(B) \leq n$</p>
<p>(7) 若$A^{- 1}$存在$\Rightarrow r(AB) = r(B);$ 若$B^{- 1}$存在
$\Rightarrow r(AB) = r(A);$</p>
<p>若$r(A_{m \times n}) = n \Rightarrow r(AB) = r(B);$ 若$r(A_{m \times s}) = n\Rightarrow r(AB) = r\left( A \right)$。</p>
<p>(8) $r(A_{m \times s}) = n \Leftrightarrow Ax = 0$只有零解</p>
<p><strong>8.分块求逆公式</strong></p>
<p>$\begin{pmatrix} A & O \\ O & B \\ \end{pmatrix}^{- 1} = \begin{pmatrix} A^{-1} & O \\ O & B^{- 1} \\ \end{pmatrix}$； $\begin{pmatrix} A & C \\ O & B \\\end{pmatrix}^{- 1} = \begin{pmatrix} A^{- 1}& - A^{- 1}CB^{- 1} \\ O & B^{- 1} \\ \end{pmatrix}$；</p>
<p>$\begin{pmatrix} A & O \\ C & B \\ \end{pmatrix}^{- 1} = \begin{pmatrix}  A^{- 1}&{O} \\   - B^{- 1}CA^{- 1} & B^{- 1} \\\end{pmatrix}$； $\begin{pmatrix} O & A \\ B & O \\ \end{pmatrix}^{- 1} =\begin{pmatrix} O & B^{- 1} \\ A^{- 1} & O \\ \end{pmatrix}$</p>
<p>这里$A$，$B$均为可逆方阵。</p>

#### 向量

<p><strong>1.有关向量组的线性表示</strong></p>
<p>(1)$\alpha_{1},\alpha_{2},\cdots,\alpha_{s}$线性相关$\Leftrightarrow$至少有一个向量可以用其余向量线性表示。</p>
<p>(2)$\alpha_{1},\alpha_{2},\cdots,\alpha_{s}$线性无关，$\alpha_{1},\alpha_{2},\cdots,\alpha_{s}$，$\beta$线性相关$\Leftrightarrow \beta$可以由$\alpha_{1},\alpha_{2},\cdots,\alpha_{s}$唯一线性表示。</p>
<p>(3) $\beta$可以由$\alpha_{1},\alpha_{2},\cdots,\alpha_{s}$线性表示
$\Leftrightarrow r(\alpha_{1},\alpha_{2},\cdots,\alpha_{s}) =r(\alpha_{1},\alpha_{2},\cdots,\alpha_{s},\beta)$ 。</p>
<p><strong>2.有关向量组的线性相关性</strong></p>
<p>(1)部分相关，整体相关；整体无关，部分无关.</p>
<p>(2) ① $n$个$n$维向量
$\alpha_{1},\alpha_{2}\cdots\alpha_{n}$线性无关$\Leftrightarrow \left|\left\lbrack \alpha_{1}\alpha_{2}\cdots\alpha_{n} \right\rbrack \right| \neq0$， $n$个$n$维向量$\alpha_{1},\alpha_{2}\cdots\alpha_{n}$线性相关
$\Leftrightarrow |\lbrack\alpha_{1},\alpha_{2},\cdots,\alpha_{n}\rbrack| = 0$
。</p>
<p>② $n + 1$个$n$维向量线性相关。</p>
<p>③ 若$\alpha_{1},\alpha_{2}\cdots\alpha_{S}$线性无关，则添加分量后仍线性无关；或一组向量线性相关，去掉某些分量后仍线性相关。</p>
<p><strong>3.有关向量组的线性表示</strong></p>
<p>(1) $\alpha_{1},\alpha_{2},\cdots,\alpha_{s}$线性相关$\Leftrightarrow$至少有一个向量可以用其余向量线性表示。</p>
<p>(2) $\alpha_{1},\alpha_{2},\cdots,\alpha_{s}$线性无关，$\alpha_{1},\alpha_{2},\cdots,\alpha_{s}$，$\beta$线性相关$\Leftrightarrow\beta$ 可以由$\alpha_{1},\alpha_{2},\cdots,\alpha_{s}$唯一线性表示。</p>
<p>(3) $\beta$可以由$\alpha_{1},\alpha_{2},\cdots,\alpha_{s}$线性表示
$\Leftrightarrow r(\alpha_{1},\alpha_{2},\cdots,\alpha_{s}) =r(\alpha_{1},\alpha_{2},\cdots,\alpha_{s},\beta)$</p>
<p><strong>4.向量组的秩与矩阵的秩之间的关系</strong></p>
<p>设$r(A_{m \times n}) =r$，则$A$的秩$r(A)$与$A$的行列向量组的线性相关性关系为：</p>
<p>(1) 若$r(A_{m \times n}) = r = m$，则$A$的行向量组线性无关。</p>
<p>(2) 若$r(A_{m \times n}) = r < m$，则$A$的行向量组线性相关。</p>
<p>(3) 若$r(A_{m \times n}) = r = n$，则$A$的列向量组线性无关。</p>
<p>(4) 若$r(A_{m \times n}) = r < n$，则$A$的列向量组线性相关。</p>
<p><strong>5.</strong>$\mathbf{n}$<strong>维向量空间的基变换公式及过渡矩阵</strong></p>
<p>若$\alpha_{1},\alpha_{2},\cdots,\alpha_{n}$与$\beta_{1},\beta_{2},\cdots,\beta_{n}$是向量空间$V$的两组基，则基变换公式为：</p>
<p>$(\beta_{1},\beta_{2},\cdots,\beta_{n}) = (\alpha_{1},\alpha_{2},\cdots,\alpha_{n})\begin{bmatrix}  c_{11}& c_{12}& \cdots & c_{1n} \\  c_{21}& c_{22}&\cdots & c_{2n} \\ \cdots & \cdots & \cdots & \cdots \\  c_{n1}& c_{n2} & \cdots & c_{nn} \\\end{bmatrix} = (\alpha_{1},\alpha_{2},\cdots,\alpha_{n})C$</p>
<p>其中$C$是可逆矩阵，称为由基$\alpha_{1},\alpha_{2},\cdots,\alpha_{n}$到基$\beta_{1},\beta_{2},\cdots,\beta_{n}$的过渡矩阵。</p>
<p><strong>6.坐标变换公式</strong></p>
<p>若向量$\gamma$在基$\alpha_{1},\alpha_{2},\cdots,\alpha_{n}$与基$\beta_{1},\beta_{2},\cdots,\beta_{n}$的坐标分别是
$X = {(x_{1},x_{2},\cdots,x_{n})}^{T}$，</p>
<p>$Y = \left( y_{1},y_{2},\cdots,y_{n} \right)^{T}$ 即： $\gamma =x_{1}\alpha_{1} + x_{2}\alpha_{2} + \cdots + x_{n}\alpha_{n} = y_{1}\beta_{1} +y_{2}\beta_{2} + \cdots + y_{n}\beta_{n}$，则向量坐标变换公式为$X = CY$ 或$Y = C^{- 1}X$，其中$C$是从基$\alpha_{1},\alpha_{2},\cdots,\alpha_{n}$到基$\beta_{1},\beta_{2},\cdots,\beta_{n}$的过渡矩阵。</p>
<p><strong>7.向量的内积</strong></p>
<p>$(\alpha,\beta) = a_{1}b_{1} + a_{2}b_{2} + \cdots + a_{n}b_{n} = \alpha^{T}\beta = \beta^{T}\alpha$</p>
<p><strong>8.Schmidt正交化</strong></p>
<p>若$\alpha_{1},\alpha_{2},\cdots,\alpha_{s}$线性无关，则可构造$\beta_{1},\beta_{2},\cdots,\beta_{s}$使其两两正交，且$\beta_{i}$仅是$\alpha_{1},\alpha_{2},\cdots,\alpha_{i}$的线性组合$(i= 1,2,\cdots,n)$，再把$\beta_{i}$单位化，记$\gamma_{i} =\frac{\beta_{i}}{\left| \beta_{i}\right|}$，则$\gamma_{1},\gamma_{2},\cdots,\gamma_{i}$是规范正交向量组。其中
$\beta_{1} = \alpha_{1}$， $\beta_{2} = \alpha_{2} -\frac{(\alpha_{2},\beta_{1})}{(\beta_{1},\beta_{1})}\beta_{1}$ ， $\beta_{3} =\alpha_{3} - \frac{(\alpha_{3},\beta_{1})}{(\beta_{1},\beta_{1})}\beta_{1} -\frac{(\alpha_{3},\beta_{2})}{(\beta_{2},\beta_{2})}\beta_{2}$ ，</p>
<p>............</p>
<p>$\beta_{s} = \alpha_{s} - \frac{(\alpha_{s},\beta_{1})}{(\beta_{1},\beta_{1})}\beta_{1} - \frac{(\alpha_{s},\beta_{2})}{(\beta_{2},\beta_{2})}\beta_{2} - \cdots - \frac{(\alpha_{s},\beta_{s - 1})}{(\beta_{s - 1},\beta_{s - 1})}\beta_{s - 1}$</p>
<p><strong>9.正交基及规范正交基</strong></p>
<p>向量空间一组基中的向量如果两两正交，就称为正交基；若正交基中每个向量都是单位向量，就称其为规范正交基。</p>

#### 线性方程组

<p><strong>1．克莱姆法则</strong></p>
<p>线性方程组$\begin{cases}  a_{11}x_{1} + a_{12}x_{2} + \cdots +a_{1n}x_{n} = b_{1} \\   a_{21}x_{1} + a_{22}x_{2} + \cdots + a_{2n}x_{n} =b_{2} \\   \quad\cdots\cdots\cdots\cdots\cdots\cdots\cdots\cdots\cdots \\ a_{n1}x_{1} + a_{n2}x_{2} + \cdots + a_{nn}x_{n} = b_{n} \\ \end{cases}$，如果系数行列式$D = \left| A \right| \neq 0$，则方程组有唯一解，$x_{1} = \frac{D_{1}}{D},x_{2} = \frac{D_{2}}{D},\cdots,x_{n} =\frac{D_{n}}{D}$，其中$D_{j}$是把$D$中第$j$列元素换成方程组右端的常数列所得的行列式。</p>
<p><strong>2.</strong> $n$阶矩阵$A$可逆$\Leftrightarrow Ax = 0$只有零解。$\Leftrightarrow\forall b,Ax = b$总有唯一解，一般地，$r(A_{m \times n}) = n \Leftrightarrow Ax= 0$只有零解。</p>
<p><strong>3.非奇次线性方程组有解的充分必要条件，线性方程组解的性质和解的结构</strong></p>
<p>(1) 设$A$为$m \times n$矩阵，若$r(A_{m \times n}) = m$，则对$Ax =b$而言必有$r(A) = r(A \vdots b) = m$，从而$Ax = b$有解。</p>
<p>(2) 设$x_{1},x_{2},\cdots x_{s}$为$Ax = b$的解，则$k_{1}x_{1} + k_{2}x_{2}\cdots + k_{s}x_{s}$当$k_{1} + k_{2} + \cdots + k_{s} = 1$时仍为$Ax =b$的解；但当$k_{1} + k_{2} + \cdots + k_{s} = 0$时，则为$Ax =0$的解。特别$\frac{x_{1} + x_{2}}{2}$为$Ax = b$的解；$2x_{3} - (x_{1} +x_{2})$为$Ax = 0$的解。</p>
<p>(3) 非齐次线性方程组${Ax} = b$无解$\Leftrightarrow r(A) + 1 =r(\overline{A}) \Leftrightarrow b$不能由$A$的列向量$\alpha_{1},\alpha_{2},\cdots,\alpha_{n}$线性表示。</p>
<p><strong>4.奇次线性方程组的基础解系和通解，解空间，非奇次线性方程组的通解</strong></p>
<p>(1) 齐次方程组${Ax} = 0$恒有解(必有零解)。当有非零解时，由于解向量的任意线性组合仍是该齐次方程组的解向量，因此${Ax}= 0$的全体解向量构成一个向量空间，称为该方程组的解空间，解空间的维数是$n - r(A)$，解空间的一组基称为齐次方程组的基础解系。</p>
<p>(2) $\eta_{1},\eta_{2},\cdots,\eta_{t}$是${Ax} = 0$的基础解系，即：</p>
<p>1) $\eta_{1},\eta_{2},\cdots,\eta_{t}$是${Ax} = 0$的解；</p>
<p>2) $\eta_{1},\eta_{2},\cdots,\eta_{t}$线性无关；</p>
<p>3) ${Ax} = 0$的任一解都可以由$\eta_{1},\eta_{2},\cdots,\eta_{t}$线性表出.
$k_{1}\eta_{1} + k_{2}\eta_{2} + \cdots + k_{t}\eta_{t}$是${Ax} = 0$的通解，其中$k_{1},k_{2},\cdots,k_{t}$是任意常数。</p>

#### 矩阵的特征值和特征向量

<p><strong>1.矩阵的特征值和特征向量的概念及性质</strong></p>
<p>(1) 设$\lambda$是$A$的一个特征值，则 ${kA},{aA} + {bE},A^{2},A^{m},f(A),A^{T},A^{- 1},A^{*}$有一个特征值分别为
${kλ},{aλ} + b,\lambda^{2},\lambda^{m},f(\lambda),\lambda,\lambda^{- 1},\frac{|A|}{\lambda},$且对应特征向量相同（$A^{T}$ 例外）。</p>
<p>(2)若$\lambda_{1},\lambda_{2},\cdots,\lambda_{n}$为$A$的$n$个特征值，则$\sum_{i= 1}^{n}\lambda_{i} = \sum_{i = 1}^{n}a_{ii},\prod_{i = 1}^{n}\lambda_{i}= |A|$ ,从而$|A| \neq 0 \Leftrightarrow A$没有特征值。</p>
<p>(3)设$\lambda_{1},\lambda_{2},\cdots,\lambda_{s}$为$A$的$s$个特征值，对应特征向量为$\alpha_{1},\alpha_{2},\cdots,\alpha_{s}$，</p>
<p>若: $\alpha = k_{1}\alpha_{1} + k_{2}\alpha_{2} + \cdots + k_{s}\alpha_{s}$ ,</p>
<p>则: $A^{n}\alpha = k_{1}A^{n}\alpha_{1} + k_{2}A^{n}\alpha_{2} + \cdots +k_{s}A^{n}\alpha_{s} = k_{1}\lambda_{1}^{n}\alpha_{1} +k_{2}\lambda_{2}^{n}\alpha_{2} + \cdots k_{s}\lambda_{s}^{n}\alpha_{s}$ 。</p>
<p><strong>2.相似变换、相似矩阵的概念及性质</strong></p>
<p>(1) 若$A \sim B$，则</p>
<p>1) $A^{T} \sim B^{T},A^{- 1} \sim B^{- 1},,A^{*} \sim B^{*}$</p>
<p>2) $|A| = |B|,\sum_{i = 1}^{n}A_{ii} = \sum_{i =1}^{n}b_{ii},r(A) = r(B)$</p>
<p>3) $|\lambda E - A| = |\lambda E - B|$，对$\forall\lambda$成立</p>
<p><strong>3.矩阵可相似对角化的充分必要条件</strong></p>
<p>(1)设$A$为$n$阶方阵，则$A$可对角化$\Leftrightarrow$对每个$k_{i}$重根特征值$\lambda_{i}$，有$n-r(\lambda_{i}E - A) = k_{i}$</p>
<p>(2) 设$A$可对角化，则由$P^{- 1}{AP} = \Lambda,$有$A = {PΛ}P^{-1}$，从而$A^{n} = P\Lambda^{n}P^{- 1}$</p>
<p>(3) 重要结论</p>
<p>1) 若$A \sim B,C \sim D​$，则$\begin{bmatrix}  A & O \\ O & C \\\end{bmatrix} \sim \begin{bmatrix} B & O \\  O & D \\\end{bmatrix}​$.</p>
<p>2) 若$A \sim B$，则$f(A) \sim f(B),\left| f(A) \right| \sim \left| f(B)\right|$，其中$f(A)$为关于$n$阶方阵$A$的多项式。</p>
<p>3) 若$A$为可对角化矩阵，则其非零特征值的个数(重根重复计算)＝秩($A$)</p>
<p><strong>4.实对称矩阵的特征值、特征向量及相似对角阵</strong></p>
<p>(1)相似矩阵：设$A,B$为两个$n$阶方阵，如果存在一个可逆矩阵$P$，使得$B =P^{- 1}{AP}$成立，则称矩阵$A$与$B$相似，记为$A \sim B$。</p>
<p>(2)相似矩阵的性质：如果$A \sim B$则有：</p>
<p>1) $A^{T} \sim B^{T}$</p>
<p>2) $A^{- 1} \sim B^{- 1}$ （若$A$，$B$均可逆）</p>
<p>3) $A^{k} \sim B^{k}$ （$k$为正整数）</p>
<p>4) $\left| {λE} - A \right| = \left| {λE} - B \right|$，从而$A,B$
有相同的特征值</p>
<p>5) $\left| A \right| = \left| B \right|$，从而$A,B$同时可逆或者不可逆</p>
<p>6) 秩$\left( A \right) =$秩$\left( B \right),\left| {λE} - A \right| =\left| {λE} - B \right|$，$A,B$不一定相似</p>

#### 二次型

<p><strong>1.</strong>$\mathbf{n}$<strong>个变量</strong>$\mathbf{x}_{\mathbf{1}}\mathbf{,}\mathbf{x}_{\mathbf{2}}\mathbf{,\cdots,}\mathbf{x}_{\mathbf{n}}$<strong>的二次齐次函数</strong></p>
<p>$f(x_{1},x_{2},\cdots,x_{n}) = \sum_{i = 1}^{n}{\sum_{j =1}^{n}{a_{ij}x_{i}y_{j}}}$，其中$a_{ij} = a_{ji}(i,j =1,2,\cdots,n)$，称为$n$元二次型，简称二次型. 若令$x = \ \begin{bmatrix}x_{1} \\ x_{1} \\  \vdots \\ x_{n} \\ \end{bmatrix},A = \begin{bmatrix}  a_{11}& a_{12}& \cdots & a_{1n} \\  a_{21}& a_{22}& \cdots & a_{2n} \\ \cdots &\cdots &\cdots &\cdots \\  a_{n1}& a_{n2} & \cdots & a_{nn} \\\end{bmatrix}$,这二次型$f$可改写成矩阵向量形式$f =x^{T}{Ax}$。其中$A$称为二次型矩阵，因为$a_{ij} =a_{ji}(i,j =1,2,\cdots,n)$，所以二次型矩阵均为对称矩阵，且二次型与对称矩阵一一对应，并把矩阵$A$的秩称为二次型的秩。</p>
<p><strong>2.惯性定理，二次型的标准形和规范形</strong></p>
<p>(1) 惯性定理</p>
<p>对于任一二次型，不论选取怎样的合同变换使它化为仅含平方项的标准型，其正负惯性指数与所选变换无关，这就是所谓的惯性定理。</p>
<p>(2) 标准形</p>
<p>二次型$f = \left( x_{1},x_{2},\cdots,x_{n} \right) =x^{T}{Ax}$经过合同变换$x = {Cy}$化为$f = x^{T}{Ax} =y^{T}C^{T}{AC}$</p>
<p>$y = \sum_{i = 1}^{r}{d_{i}y_{i}^{2}}$称为 $f(r \leq n)$的标准形。在一般的数域内，二次型的标准形不是唯一的，与所作的合同变换有关，但系数不为零的平方项的个数由$r(A)$唯一确定。</p>
<p>(3) 规范形</p>
<p>任一实二次型$f$都可经过合同变换化为规范形$f = z_{1}^{2} + z_{2}^{2} + \cdots z_{p}^{2} - z_{p + 1}^{2} - \cdots -z_{r}^{2}$，其中$r$为$A$的秩，$p$为正惯性指数，$r -p$为负惯性指数，且规范型唯一。</p>
<p><strong>3.用正交变换和配方法化二次型为标准形，二次型及其矩阵的正定性</strong></p>
<p>设$A$正定$\Rightarrow {kA}(k > 0),A^{T},A^{- 1},A^{*}$正定；$|A| >0$,$A$可逆；$a_{ii} > 0$，且$|A_{ii}| > 0$</p>
<p>$A$，$B$正定$\Rightarrow A +B$正定，但${AB}$，${BA}$不一定正定</p>
<p>$A$正定$\Leftrightarrow f(x) = x^{T}{Ax} > 0,\forall x \neq 0$</p>
<p>$\Leftrightarrow A$的各阶顺序主子式全大于零</p>
<p>$\Leftrightarrow A$的所有特征值大于零</p>
<p>$\Leftrightarrow A$的正惯性指数为$n$</p>
<p>$\Leftrightarrow$存在可逆阵$P$使$A = P^{T}P$</p>
<p>$\Leftrightarrow$存在正交矩阵$Q$，使$Q^{T}{AQ} = Q^{- 1}{AQ} =\begin{pmatrix} \lambda_{1} & & \\ \begin{matrix}  & \\  & \\ \end{matrix} &\ddots & \\  & & \lambda_{n} \\ \end{pmatrix},$</p>
<p>其中$\lambda_{i} > 0,i = 1,2,\cdots,n.$正定$\Rightarrow {kA}(k >0),A^{T},A^{- 1},A^{*}$正定； $|A| > 0,A$可逆；$a_{ii} >0$，且$|A_{ii}| > 0$ 。</p>

### 概率论和数理统计

#### 随机事件和概率

<p><strong>1.事件的关系与运算</strong></p>
<p>(1) 子事件：$A \subset B$，若$A$发生，则$B$发生。</p>
<p>(2) 相等事件：$A = B$，即$A \subset B$，且$B \subset A$ 。</p>
<p>(3) 和事件：$A\bigcup B$（或$A + B$），$A$与$B$中至少有一个发生。</p>
<p>(4) 差事件：$A - B$，$A$发生但$B$不发生。</p>
<p>(5) 积事件：$A\bigcap B$（或${AB}$），$A$与$B$同时发生。</p>
<p>(6) 互斥事件（互不相容）：$A\bigcap B$=$\varnothing$。</p>
<p>(7) 互逆事件（对立事件）：
$A\bigcap B=\varnothing ,A\bigcup B=\Omega ,A=\bar{B},B=\bar{A}$
<strong>2.运算律</strong>
(1) 交换律：$A\bigcup B=B\bigcup A,A\bigcap B=B\bigcap A$
(2) 结合律：$(A\bigcup B)\bigcup C=A\bigcup (B\bigcup C)$
(3) 分配律：$(A\bigcap B)\bigcap C=A\bigcap (B\bigcap C)$
<strong>3.德$\centerdot $摩根律</strong></p>
<p>$\overline{A\bigcup B}=\bar{A}\bigcap \bar{B}$                 $\overline{A\bigcap B}=\bar{A}\bigcup \bar{B}$
<strong>4.完全事件组</strong> </p>
<p>${a_{1}}{a_{2}}\cdots {a_{n}}$两两互斥，且和事件为必然事件，即${A_{i}}\bigcap A_{j}=\varnothing$, $i\ne j$, $\mathop \bigcup_{i=1}^n =\Omega$</p>
<p><strong>5.概率的基本公式</strong>
(1)条件概率:
 $P(B|A)=\frac{P(AB)}{P(A)}$,表示$A$发生的条件下，$B$发生的概率。
(2)全概率公式：
$P(A)=\sum\limits_{i=1}^{n}{P(A|{B_{i}})P({B_{i}}),{B_{i}}{B_{j}}}=\varnothing ,i\ne j,\underset{i=1}{\overset{n}{\mathop{\bigcup }}}\,{B_{i}}=\Omega $
(3) Bayes公式：</p>
<p>$P({B_{j}}|A)=\frac{P(A|{B_{j}})P({B_{j}})}{\sum\limits_{i=1}^{n}{P(A|{B_{i}})P({B_{i}})}},j=1,2,\cdots ,n$
注：上述公式中事件${B_{i}}$的个数可为可列个。
(4)乘法公式：
$P({a_{1}}{a_{2}})=P({a_{1}})P({a_{2}}|{a_{1}})=P({a_{2}})P({a_{1}}|{a_{2}})$
$P({a_{1}}{a_{2}}\cdots {a_{n}})=P({a_{1}})P({a_{2}}|{a_{1}})P({a_{3}}|{a_{1}}{a_{2}})\cdots P({a_{n}}|{a_{1}}{a_{2}}\cdots {a_{n-1}})$</p>
<p><strong>6.事件的独立性</strong>
(1)$A$与$B$相互独立$\Leftrightarrow P(AB)=P(A)P(B)$
(2)$A$，$B$，$C$两两独立
$\Leftrightarrow P(AB)=P(A)P(B)$;$P(BC)=P(B)P(C)$ ;$P(AC)=P(A)P(C)$;
(3)$A$，$B$，$C$相互独立
$\Leftrightarrow P(AB)=P(A)P(B)$;     $P(BC)=P(B)P(C)$ ;
$P(AC)=P(A)P(C)$  ;   $P(ABC)=P(A)P(B)P(C)$</p>
<p><strong>7.独立重复试验</strong> </p>
<p>将某试验独立重复$n$次，若每次实验中事件A发生的概率为$p$，则$n$次试验中$A$发生$k$次的概率为：
$P(X=k)=C_{n}^{k}{p^{k}}{(1-p)^{n-k}}$
<strong>8.重要公式与结论</strong>
$(1)P(\bar{A})=1-P(A)$
$(2)P(A\bigcup B)=P(A)+P(B)-P(AB)$
   $P(A\bigcup B\bigcup C)=P(A)+P(B)+P(C)-P(AB)-P(BC)-P(AC)+P(ABC)$
$(3)P(A-B)=P(A)-P(AB)$
$(4)P(A\bar{B})=P(A)-P(AB),P(A)=P(AB)+P(A\bar{B}),$
 $P(A\bigcup B)=P(A)+P(\bar{A}B)=P(AB)+P(A\bar{B})+P(\bar{A}B)$
(5)条件概率$P(\centerdot |B)$满足概率的所有性质，
例如：. $P({\bar{A}_{1}}|B)=1-P({a_{1}}|B)$
$P({a_{1}}\bigcup {a_{2}}|B)=P({a_{1}}|B)+P({a_{2}}|B)-P({a_{1}}{a_{2}}|B)$
$P({a_{1}}{a_{2}}|B)=P({a_{1}}|B)P({a_{2}}|{a_{1}}B)$
(6)若${a_{1}},{a_{2}},\cdots ,{a_{n}}$相互独立，则$P(\bigcap\limits_{i=1}^{n}{a_{i}})=\prod\limits_{i=1}^{n}{P({a_{i}})},$
 $P(\bigcup\limits_{i=1}^{n}{a_{i}})=\prod\limits_{i=1}^{n}{(1-P({a_{i}}))}$
(7)互斥、互逆与独立性之间的关系：
$A$与$B$互逆$\Rightarrow$ $A$与$B$互斥，但反之不成立，$A$与$B$互斥（或互逆）且均非零概率事件$\Rightarrow $$A$与$B$不独立.
(8)若${A_{1}},{A_{2}},\cdots ,{A_{m}},{B_{1}},{B_{2}},\cdots ,{B_{n}}$相互独立，则$f({A_{1}},{A_{2}},\cdots ,{A_{m}})$与$g({B_{1}},{B_{2}},\cdots ,{B_{n}})$也相互独立，其中$f(\centerdot)$, $g(\centerdot)$分别表示对相应事件做任意事件运算后所得的事件，另外，概率为1（或0）的事件与任何事件相互独立.</p>
<p>&nbsp;</p>

#### 随机变量及其概率分布

<p><strong>1.随机变量及概率分布</strong></p>
<p>取值带有随机性的变量，严格地说是定义在样本空间上，取值于实数的函数称为随机变量，概率分布通常指分布函数或分布律</p>
<p><strong>2.分布函数的概念与性质</strong></p>
<p>定义： $F(x) = P(X \leq x), - \infty < x < + \infty$</p>
<p>性质：(1)$0 \leq F(x) \leq 1$ </p>
<p>(2) $F(x)$单调不减</p>
<p>(3) 右连续$F(x + 0) = F(x)$ </p>
<p>(4) $F( - \infty) = 0,F( + \infty) = 1$</p>
<p><strong>3.离散型随机变量的概率分布</strong></p>
<p>$P(X = x_{i}) = p_{i},i = 1,2,\cdots,n,\cdots\quad\quad p_{i} \geq 0,\sum_{i =1}^{\infty}p_{i} = 1$</p>
<p><strong>4.连续型随机变量的概率密度</strong></p>
<p>概率密度$f(x)$;非负可积，且:</p>
<p>(1)$f(x) \geq 0,$ </p>
<p>(2)$\int_{- \infty}^{+\infty}{f(x){dx} = 1}$ </p>
<p>(3)$x$为$f(x)$的连续点，则:</p>
<p>$f(x) = F'(x)$分布函数$F(x) = \int_{- \infty}^{x}{f(t){dt}}$</p>
<p><strong>5.常见分布</strong></p>
<p>(1) 0-1分布:$P(X = k) = p^{k}{(1 - p)}^{1 - k},k = 0,1$</p>
<p>(2) 二项分布:$B(n,p)$： $P(X = k) = C_{n}^{k}p^{k}{(1 - p)}^{n - k},k =0,1,\cdots,n$</p>
<p>(3) <strong>Poisson</strong>分布:$p(\lambda)$： $P(X = k) = \frac{\lambda^{k}}{k!}e^{-\lambda},\lambda > 0,k = 0,1,2\cdots$</p>
<p>(4) 均匀分布$U(a,b)$：$f(x) = \{ \begin{matrix}  & \frac{1}{b - a},a < x< b \\  & 0, \\ \end{matrix} $</p>
<p>(5) 正态分布:$N(\mu,\sigma^{2}):$ $\varphi(x) =\frac{1}{\sqrt{2\pi}\sigma}e^{- \frac{(x - \mu)^{2}}{2\sigma^{2}}},\sigma > 0,\infty < x < + \infty$</p>
<p>(6)指数分布:$E(\lambda):f(x) =\{ \begin{matrix}  & \lambda e^{-{λx}},x > 0,\lambda > 0 \\  & 0, \\ \end{matrix} $</p>
<p>(7)几何分布:$G(p):P(X = k) = {(1 - p)}^{k - 1}p,0 < p < 1,k = 1,2,\cdots.$</p>
<p>(8)超几何分布: $H(N,M,n):P(X = k) = \frac{C_{M}^{k}C_{N - M}^{n -k}}{C_{N}^{n}},k =0,1,\cdots,min(n,M)$</p>
<p><strong>6.随机变量函数的概率分布</strong></p>
<p>(1)离散型：$P(X = x_{1}) = p_{i},Y = g(X)$</p>
<p>则: $P(Y = y_{j}) = \sum_{g(x_{i}) = y_{i}}^{}{P(X = x_{i})}$</p>
<p>(2)连续型：$X\tilde{\ }f_{X}(x),Y = g(x)$</p>
<p>则:$F_{y}(y) = P(Y \leq y) = P(g(X) \leq y) = \int_{g(x) \leq y}^{}{f_{x}(x)dx}$， $f_{Y}(y) = F'_{Y}(y)$</p>
<p><strong>7.重要公式与结论</strong></p>
<p>(1) $X\sim N(0,1) \Rightarrow \varphi(0) = \frac{1}{\sqrt{2\pi}},\Phi(0) =\frac{1}{2},$ $\Phi( - a) = P(X \leq - a) = 1 - \Phi(a)$</p>
<p>(2) $X\sim N\left( \mu,\sigma^{2} \right) \Rightarrow \frac{X -\mu}{\sigma}\sim N\left( 0,1 \right),P(X \leq a) = \Phi(\frac{a -\mu}{\sigma})$</p>
<p>(3) $X\sim E(\lambda) \Rightarrow P(X > s + t|X > s) = P(X > t)$</p>
<p>(4) $X\sim G(p) \Rightarrow P(X = m + k|X > m) = P(X = k)$</p>
<p>(5) 离散型随机变量的分布函数为阶梯间断函数；连续型随机变量的分布函数为连续函数，但不一定为处处可导函数。</p>
<p>(6) 存在既非离散也非连续型随机变量。</p>

#### 多维随机变量及其分布

<p><strong>1.二维随机变量及其联合分布</strong></p>
<p>由两个随机变量构成的随机向量$(X,Y)$， 联合分布为$F(x,y) = P(X \leq x,Y \leq y)$</p>
<p><strong>2.二维离散型随机变量的分布</strong></p>
<p>(1) 联合概率分布律 $P\{ X = x_{i},Y = y_{j}\} = p_{ij};i,j =1,2,\cdots$</p>
<p>(2) 边缘分布律 $p_{i \cdot} = \sum_{j = 1}^{\infty}p_{ij},i =1,2,\cdots$ $p_{\cdot j} = \sum_{i}^{\infty}p_{ij},j = 1,2,\cdots$</p>
<p>(3) 条件分布律 $P\{ X = x_{i}|Y = y_{j}\} = \frac{p_{ij}}{p_{\cdot j}}$
$P\{ Y = y_{j}|X = x_{i}\} = \frac{p_{ij}}{p_{i \cdot}}$</p>
<p><strong>3. 二维连续性随机变量的密度</strong></p>
<p>(1) 联合概率密度$f(x,y):$</p>
<p>1) $f(x,y) \geq 0$ </p>
<p>2) $\int_{- \infty}^{+ \infty}{\int_{- \infty}^{+ \infty}{f(x,y)dxdy}} = 1$</p>
<p>(2) 分布函数：$F(x,y) = \int_{- \infty}^{x}{\int_{- \infty}^{y}{f(u,v)dudv}}$</p>
<p>(3) 边缘概率密度： $f_{X}\left( x \right) = \int_{- \infty}^{+ \infty}{f\left( x,y \right){dy}}$ $f_{Y}(y) = \int_{- \infty}^{+ \infty}{f(x,y)dx}$</p>
<p>(4) 条件概率密度：$f_{X|Y}\left( x \middle| y \right) = \frac{f\left( x,y \right)}{f_{Y}\left( y \right)}$ $f_{Y|X}(y|x) = \frac{f(x,y)}{f_{X}(x)}$</p>
<p><strong>4.常见二维随机变量的联合分布</strong></p>
<p>(1) 二维均匀分布：$(x,y) \sim U(D)$ ,$f(x,y) = \begin{cases} \frac{1}{S(D)},(x,y) \in D \\   0,其他  \end{cases}$</p>
<p>(2) 二维正态分布：$(X,Y)\sim N(\mu_{1},\mu_{2},\sigma_{1}^{2},\sigma_{2}^{2},\rho)$,$(X,Y)\sim N(\mu_{1},\mu_{2},\sigma_{1}^{2},\sigma_{2}^{2},\rho)$</p>
<p>$f(x,y) = \frac{1}{2\pi\sigma_{1}\sigma_{2}\sqrt{1 - \rho^{2}}}.\exp\left\{ \frac{- 1}{2(1 - \rho^{2})}\lbrack\frac{(x - \mu_{1})^{2}}{\sigma_{1}^{2}} - 2\rho\frac{(x - \mu_{1})(y - \mu_{2})}{\sigma_{1}\sigma_{2}} + \frac{(y - \mu_{2})^{2}}{\sigma_{2}^{2}}\rbrack \right\}$</p>
<p><strong>5.随机变量的独立性和相关性</strong></p>
<p>$X$和$Y$的相互独立:$\Leftrightarrow F\left( x,y \right) = F_{X}\left( x \right)F_{Y}\left( y \right)$:</p>
<p>$\Leftrightarrow p_{ij} = p_{i \cdot} \cdot p_{\cdot j}$（离散型）
$\Leftrightarrow f\left( x,y \right) = f_{X}\left( x \right)f_{Y}\left( y \right)$（连续型）</p>
<p>$X$和$Y$的相关性：</p>
<p>相关系数$\rho_{XY} = 0$时，称$X$和$Y$不相关，
否则称$X$和$Y$相关</p>
<p><strong>6.两个随机变量简单函数的概率分布</strong></p>
<p>离散型： $P\left( X = x_{i},Y = y_{i} \right) = p_{ij},Z = g\left( X,Y \right)$ 则：</p>
<p>$P(Z = z_{k}) = P\left\{ g\left( X,Y \right) = z_{k} \right\} = \sum_{g\left( x_{i},y_{i} \right) = z_{k}}^{}{P\left( X = x_{i},Y = y_{j} \right)}$</p>
<p>连续型： $\left( X,Y \right) \sim f\left( x,y \right),Z = g\left( X,Y \right)$
则：</p>
<p>$F_{z}\left( z \right) = P\left\{ g\left( X,Y \right) \leq z \right\} = \iint_{g(x,y) \leq z}^{}{f(x,y)dxdy}$，$f_{z}(z) = F'_{z}(z)$</p>
<p><strong>7.重要公式与结论</strong></p>
<p>(1) 边缘密度公式： $f_{X}(x) = \int_{- \infty}^{+ \infty}{f(x,y)dy,}$
$f_{Y}(y) = \int_{- \infty}^{+ \infty}{f(x,y)dx}$</p>
<p>(2) $P\left\{ \left( X,Y \right) \in D \right\} = \iint_{D}^{}{f\left( x,y \right){dxdy}}$</p>
<p>(3) 若$(X,Y)$服从二维正态分布$N(\mu_{1},\mu_{2},\sigma_{1}^{2},\sigma_{2}^{2},\rho)$
则有：</p>
<p>1) $X\sim N\left( \mu_{1},\sigma_{1}^{2} \right),Y\sim N(\mu_{2},\sigma_{2}^{2}).$</p>
<p>2) $X$与$Y$相互独立$\Leftrightarrow \rho = 0$，即$X$与$Y$不相关。</p>
<p>3) $C_{1}X + C_{2}Y\sim N(C_{1}\mu_{1} + C_{2}\mu_{2},C_{1}^{2}\sigma_{1}^{2} + C_{2}^{2}\sigma_{2}^{2} + 2C_{1}C_{2}\sigma_{1}\sigma_{2}\rho)$</p>
<p>4) ${\ X}$关于$Y=y$的条件分布为： $N(\mu_{1} + \rho\frac{\sigma_{1}}{\sigma_{2}}(y - \mu_{2}),\sigma_{1}^{2}(1 - \rho^{2}))$</p>
<p>5) $Y$关于$X = x$的条件分布为： $N(\mu_{2} + \rho\frac{\sigma_{2}}{\sigma_{1}}(x - \mu_{1}),\sigma_{2}^{2}(1 - \rho^{2}))$</p>
<p>(4) 若$X$与$Y$独立，且分别服从$N(\mu_{1},\sigma_{1}^{2}),N(\mu_{1},\sigma_{2}^{2}),$
则：$\left( X,Y \right)\sim N(\mu_{1},\mu_{2},\sigma_{1}^{2},\sigma_{2}^{2},0),$</p>
<p>$C_{1}X + C_{2}Y\tilde{\ }N(C_{1}\mu_{1} + C_{2}\mu_{2},C_{1}^{2}\sigma_{1}^{2} C_{2}^{2}\sigma_{2}^{2}).$</p>
<p>(5) 若$X$与$Y$相互独立，$f\left( x \right)$和$g\left( x \right)$为连续函数， 则$f\left( X \right)$和$g(Y)$也相互独立。</p>

#### 随机变量的数字特征

<p><strong>1.数学期望</strong></p>
<p>离散型：$P\left\{ X = x_{i} \right\} = p_{i},E(X) = \sum_{i}^{}{x_{i}p_{i}}$；</p>
<p>连续型： $X\sim f(x),E(X) = \int_{- \infty}^{+ \infty}{xf(x)dx}$</p>
<p>性质：</p>
<p>(1) $E(C) = C,E\lbrack E(X)\rbrack = E(X)$</p>
<p>(2) $E(C_{1}X + C_{2}Y) = C_{1}E(X) + C_{2}E(Y)$</p>
<p>(3) 若$X$和$Y$独立，则$E(XY) = E(X)E(Y)$ </p>
<p>(4)$\left\lbrack E(XY) \right\rbrack^{2} \leq E(X^{2})E(Y^{2})$</p>
<p><strong>2.方差</strong>：$D(X) = E\left\lbrack X - E(X) \right\rbrack^{2} = E(X^{2}) - \left\lbrack E(X) \right\rbrack^{2}$</p>
<p><strong>3.标准差</strong>：$\sqrt{D(X)}$，</p>
<p><strong>4.离散型：</strong>$D(X) = \sum_{i}^{}{\left\lbrack x_{i} - E(X) \right\rbrack^{2}p_{i}}$</p>
<p><strong>5.连续型：</strong>$D(X) = {\int_{- \infty}^{+ \infty}\left\lbrack x - E(X) \right\rbrack}^{2}f(x)dx$</p>
<p>性质：</p>
<p>(1)$\ D(C) = 0,D\lbrack E(X)\rbrack = 0,D\lbrack D(X)\rbrack = 0$</p>
<p>(2) $X$与$Y$相互独立，则$D(X \pm Y) = D(X) + D(Y)$</p>
<p>(3)$\ D\left( C_{1}X + C_{2} \right) = C_{1}^{2}D\left( X \right)$</p>
<p>(4) 一般有 $D(X \pm Y) = D(X) + D(Y) \pm 2Cov(X,Y) = D(X) + D(Y) \pm 2\rho\sqrt{D(X)}\sqrt{D(Y)}$</p>
<p>(5)$\ D\left( X \right) < E\left( X - C \right)^{2},C \neq E\left( X \right)$</p>
<p>(6)$\ D(X) = 0 \Leftrightarrow P\left\{ X = C \right\} = 1$</p>
<p><strong>6.随机变量函数的数学期望</strong></p>
<p>(1) 对于函数$Y = g(x)$</p>
<p>$X$为离散型：$P\{ X = x_{i}\} = p_{i},E(Y) = \sum_{i}^{}{g(x_{i})p_{i}}$；</p>
<p>$X$为连续型：$X\sim f(x),E(Y) = \int_{- \infty}^{+ \infty}{g(x)f(x)dx}$</p>
<p>(2) $Z = g(X,Y)$;$\left( X,Y \right)\sim P\{ X = x_{i},Y = y_{j}\} = p_{ij}$; $E(Z) = \sum_{i}^{}{\sum_{j}^{}{g(x_{i},y_{j})p_{ij}}}$ $\left( X,Y \right)\sim f(x,y)$;$E(Z) = \int_{- \infty}^{+ \infty}{\int_{- \infty}^{+ \infty}{g(x,y)f(x,y)dxdy}}$</p>
<p><strong>7.协方差</strong> </p>
<p>$Cov(X,Y) = E\left\lbrack (X - E(X)(Y - E(Y)) \right\rbrack$</p>
<p><strong>8.相关系数</strong></p>
<p> $\rho_{XY} = \frac{Cov(X,Y)}{\sqrt{D(X)}\sqrt{D(Y)}}$,$k$阶原点矩 $E(X^{k})$;
$k$阶中心矩 $E\left\{ {\lbrack X - E(X)\rbrack}^{k} \right\}$</p>
<p>性质：</p>
<p>(1)$\ Cov(X,Y) = Cov(Y,X)$</p>
<p>(2)$\ Cov(aX,bY) = abCov(Y,X)$</p>
<p>(3)$\ Cov(X_{1} + X_{2},Y) = Cov(X_{1},Y) + Cov(X_{2},Y)$</p>
<p>(4)$\ \left| \rho\left( X,Y \right) \right| \leq 1$</p>
<p>(5) $\ \rho\left( X,Y \right) = 1 \Leftrightarrow P\left( Y = aX + b \right) = 1$ ，其中$a > 0$</p>
<p>$\rho\left( X,Y \right) = - 1 \Leftrightarrow P\left( Y = aX + b \right) = 1$
，其中$a < 0$</p>
<p><strong>9.重要公式与结论</strong></p>
<p>(1)$\ D(X) = E(X^{2}) - E^{2}(X)$</p>
<p>(2)$\ Cov(X,Y) = E(XY) - E(X)E(Y)$</p>
<p>(3) $\left| \rho\left( X,Y \right) \right| \leq 1,$且 $\rho\left( X,Y \right) = 1 \Leftrightarrow P\left( Y = aX + b \right) = 1$，其中$a > 0$</p>
<p>$\rho\left( X,Y \right) = - 1 \Leftrightarrow P\left( Y = aX + b \right) = 1$，其中$a < 0$</p>
<p>(4) 下面5个条件互为充要条件：</p>
<p>$\rho(X,Y) = 0$ $\Leftrightarrow Cov(X,Y) = 0$ $\Leftrightarrow E(X,Y) = E(X)E(Y)$ $\Leftrightarrow D(X + Y) = D(X) + D(Y)$ $\Leftrightarrow  D(X - Y) = D(X) + D(Y)$</p>
<p>注：$X$与$Y$独立为上述5个条件中任何一个成立的充分条件，但非必要条件。</p>

#### 数理统计的基本概念

<p><strong>1.基本概念</strong></p>
<p>总体：研究对象的全体，它是一个随机变量，用$X$表示。</p>
<p>个体：组成总体的每个基本元素。</p>
<p>简单随机样本：来自总体$X$的$n$个相互独立且与总体同分布的随机变量$X_{1},X_{2}\cdots,X_{n}$，称为容量为$n$的简单随机样本，简称样本。</p>
<p>统计量：设$X_{1},X_{2}\cdots,X_{n},$是来自总体$X$的一个样本，$g(X_{1},X_{2}\cdots,X_{n})$）是样本的连续函数，且$g()$中不含任何未知参数，则称$g(X_{1},X_{2}\cdots,X_{n})$为统计量。</p>
<p>样本均值：$\overline{X} = \frac{1}{n}\sum_{i = 1}^{n}X_{i}$</p>
<p>样本方差：$S^{2} = \frac{1}{n - 1}\sum_{i = 1}^{n}{(X_{i} - \overline{X})}^{2}$</p>
<p>样本矩：样本$k$阶原点矩：$A_{k} = \frac{1}{n}\sum_{i = 1}^{n}X_{i}^{k},k = 1,2,\cdots$</p>
<p>样本$k$阶中心矩：$B_{k} = \frac{1}{n}\sum_{i = 1}^{n}{(X_{i} - \overline{X})}^{k},k = 1,2,\cdots$</p>
<p><strong>2.分布</strong></p>
<p>$\chi^{2}$分布：$\chi^{2} = X_{1}^{2} + X_{2}^{2} + \cdots + X_{n}^{2}\sim\chi^{2}(n)$，其中$X_{1},X_{2}\cdots,X_{n},$相互独立，且同服从$N(0,1)$</p>
<p>$t$分布：$T = \frac{X}{\sqrt{Y/n}}\sim t(n)$ ，其中$X\sim N\left( 0,1 \right),Y\sim\chi^{2}(n),$且$X$，$Y$ 相互独立。</p>
<p>$F$分布：$F = \frac{X/n_{1}}{Y/n_{2}}\sim F(n_{1},n_{2})$，其中$X\sim\chi^{2}\left( n_{1} \right),Y\sim\chi^{2}(n_{2}),$且$X$，$Y$相互独立。</p>
<p>分位数：若$P(X \leq x_{\alpha}) = \alpha,$则称$x_{\alpha}$为$X$的$\alpha$分位数</p>
<p><strong>3.正态总体的常用样本分布</strong></p>
<p>(1) 设$X_{1},X_{2}\cdots,X_{n}$为来自正态总体$N(\mu,\sigma^{2})$的样本，</p>
<p>$\overline{X} = \frac{1}{n}\sum_{i = 1}^{n}X_{i},S^{2} = \frac{1}{n - 1}\sum_{i = 1}^{n}{(X_{i} - \overline{X})^{2},}$则：</p>
<p>1) $\overline{X}\sim N\left( \mu,\frac{\sigma^{2}}{n} \right){\ \ }$或者$\frac{\overline{X} - \mu}{\frac{\sigma}{\sqrt{n}}}\sim N(0,1)$</p>
<p>2) $\frac{(n - 1)S^{2}}{\sigma^{2}} = \frac{1}{\sigma^{2}}\sum_{i = 1}^{n}{(X_{i} - \overline{X})^{2}\sim\chi^{2}(n - 1)}$</p>
<p>3) $\frac{1}{\sigma^{2}}\sum_{i = 1}^{n}{(X_{i} - \mu)^{2}\sim\chi^{2}(n)}$</p>
<p>4)${\ \ }\frac{\overline{X} - \mu}{S/\sqrt{n}}\sim t(n - 1)$</p>
<p><strong>4.重要公式与结论</strong></p>
<p>(1) 对于$\chi^{2}\sim\chi^{2}(n)$，有$E(\chi^{2}(n)) = n,D(\chi^{2}(n)) = 2n;$</p>
<p>(2) 对于$T\sim t(n)$，有$E(T) = 0,D(T) = \frac{n}{n - 2}(n > 2)$；</p>
<p>(3) 对于$F\tilde{\ }F(m,n)$，有 $\frac{1}{F}\sim F(n,m),F_{a/2}(m,n) = \frac{1}{F_{1 - a/2}(n,m)};$</p>
<p>(4) 对于任意总体$X$，有 $E(\overline{X}) = E(X),E(S^{2}) = D(X),D(\overline{X}) = \frac{D(X)}{n}$</p>
