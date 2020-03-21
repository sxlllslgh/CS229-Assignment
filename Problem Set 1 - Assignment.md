# Problem Set 1 - Assignment

## 1. Newton’s method for computing least squares

- Find the *Hessian* of the cost function $J(θ) = \frac{1}{2} \sum^m_{i = 1} (\theta^T x^{(i)} - y^{(i)})^2$

**Answer**: 
$$\frac{\partial J(\theta)}{\partial \theta_j} = \sum^m_{i = 1} (\theta^T x^{(i)} - y^{(i)}) x^{(i)}_j$$
$$\begin{aligned}
\frac{\partial^2 J(\theta)}{\partial \theta_j\partial \theta_k} &=& \frac{\partial}{\partial \theta_k} \frac{\partial J(\theta)}{\partial \theta_j} \\
&=& \frac{\partial}{\partial \theta_k} \sum^m_{i = 1} (\theta^T x^{(i)} - y^{(i)}) x^{(i)}_j \\
&=& \sum^m_{i = 1} \frac{\partial}{\partial \theta_k} (\theta^T x^{(i)} - y^{(i)}) x^{(i)}_j \\
&=& \sum^m_{i = 1} x^{(i)}_j x^{(i)}_k \\
&=& (X^TX)_{jk}
\end{aligned}$$
- Show that the first iteration of Newton’s method gives us $θ^* = (X^T X)^{-1} X^T \vec{y}$, the solution to our least squares problem.