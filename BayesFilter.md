### BayesFilter滤波概率论基础知识

 1. **联合概率**：$p(X=x and Y=y)=p(x,y)$

    ​	如果$X Y$相互独立，那么$p(x,y)=p(x)p(y)$  

	2. **条件概率**：

    ​	$p(x|y)=p(x,y)/p(y)$

    ​	$p(x,y)=p(x|y)p(y)$

    ​	同样的，如果x,y相互独立，那么$p(x|y)=p(x)$

	3. **全概率公式**：

    ​	离散情况下：$p(x)=\sum p(x,y)=\sum_{y}p(x|y)p(y)$

    ​	连续情况下：$p(x)=∫p(x,y)dy=∫p(x|y)p(y)dy$

	4. ***==>>贝叶斯公式***：

    ​	$p(x|y)={\frac {p(y|x)p(x)}{p(y)}}$

    ​	其中$p(y)=\sum{p(y|x)p(x)}$

    ​	而$p(y)$和$p(x|y)$无关，故此可以将其归一化为$\eta=p(y)^{-1}$

    ​	==>> $p(x|y)=\eta*p(y|x)p(x)$ 其中y称为观测量，x称为预测量--即使用观测量对状态进行猜测推理

    三维下贝叶斯公式的推倒：
    $$
    p(x|y,z)=\frac{p(x,y,z)}{p(y,z)}=\frac{p(y|x,z)p(x,z)}{p(y,z)}=\frac{p(y|x,z)p(x|z)p(z)}{p(y|z)p(z)}=\frac{p(y|x,z)p(x|z)}{p(y|z)}
    $$
    继续推到贝叶斯递推公式：
    $$
    \begin{align*}
    p(x|z_1,z_2,...z_n)
    &=\frac{p(z_n|x,z_1,z_2,...z_{n-1})p(x|z_1,z_2,...z_{n-1})}{p(z_n|z_1,z_2,...z_{n-1})}\\
    &=\eta_1{p(z_n|x,z_1,z_2,...z_{n-1})p(x|z_1,z_2,...z_{n-1})}\\
    &=\eta_1{{p(z_n|x)p(x|z_1,z_2,...z_{n-1})}}
    \end{align*}
    $$
    *补充*：

     1. **Markov属性**：***在$x(状态)$已知的情况下(此为前提条件）***，$z_n$同${z_1,z_2,...z_{n-1}}$无关，

        即：$p(z_n|x,z_1,z_2,...z_{n-1})=p(z_n|x)$

    	2. 注意使用全概率公式


Reference：https://www.cnblogs.com/ycwang16/p/5995702.html