[[1,2,1 - Principal Components Analysis]] $\leftarrow$ Back

---

$$
M\vec{e} = \lambda\vec{e}
$$
Let there be some matrix B such that...
$$
B=\begin{bmatrix}  
\lambda & 0\\  
0 & \lambda  
\end{bmatrix}
$$
- Leading diagonal of matrix B consists of eigenvalues.
- All other elements = 0.

$$
B = \lambda\begin{bmatrix}  
1 & 0\\  
0 & 1  
\end{bmatrix}
$$
$$
\begin{bmatrix}  
1 & 0\\  
0 & 1  
\end{bmatrix} = I_{2^2}
$$
$$
B=\lambda I_{2^2}
$$

$$
M\vec{e} = B\vec{e} \wedge B=\lambda I_{2^2} \Rightarrow M\vec{e} = (\lambda I_{2^2})\vec{e}
$$
Rearranging equation so that it is equal to 0.

$$
M\vec{e}=(\lambda I_{2^2})\vec{e} \Rightarrow M\vec{e}-(\lambda I_{2^2})\vec{e} = 0
$$
Simplifying equation...
- Factorising $\vec{e}$
$$
M\vec{e}-(\lambda I_{2^2})\vec{e} = 0 \Rightarrow \vec{e}(M-\lambda I_{2^2}) = 0
$$

$$
M-\lambda I_{2^2} = \begin{bmatrix}  
m_{(1,1)}-\lambda & m_{(1,2)}\\  
m_{(2,1)} & m_{(2,2)}-\lambda  
\end{bmatrix}
$$
Solve for values of $\lambda$ which can cause $det(M-\lambda I_{2^2}) = 0$

$$
det(M-\lambda I_{2^2})=(m_{(1,1)}-\lambda)(m_{(2,2)}-\lambda)-m_{(1,2)}m_{(2,1)}
$$
$$
(m_{(1,1)}-\lambda)(m_{(2,2)}-\lambda)=m_{(1,1)}m_{(2,2)}-\lambda m_{(1,1)}-\lambda m_{(2,2)} + \lambda^2
$$
$$
m_{(1,1)}m_{(2,2)}-\lambda m_{(1,1)}-\lambda m_{(2,2)} + \lambda^2 = m_{(1,1)}m_{(2,2)}-\lambda(m_{(1,1)}+m_{(2,2)}) + \lambda^2
$$
$$
det(M-\lambda I_{2^2}) = m_{(1,1)}m_{(2,2)}-\lambda(m_{(1,1)}+m_{(2,2)})+\lambda^2 - m_{(1,2)}m_{(2,1)}
$$

$$
det(M-\lambda I_{2^2}) = 0 \Rightarrow m_{(1,1)}m_{(2,2)}-\lambda(m_{(1,1)}+m_{(2,2)})+\lambda^2 - m_{(1,2)}m_{(2,1)} = 0
$$
Solve for zeros of equation to identify all possible values of $\lambda$ which satisfy the above equation.
- In this case, equation is a quadratic. Applying the quadratic formula.

$$
\lambda^2 - \lambda(m_{(1,1)}+m_{(2,2)})+(m_{(1,1)}m_{(2,2)}-m_{(1,2)}m_{(2,1)})
$$
- $a = 1$
- $b = (m_{(1,1)} + m_{(2,2)})$
- $c = (m_{(1,1)}m_{(2,2)}-m_{(1,2)}m_{(2,1)})$

$$
\lambda = \frac{-(m_{(1,1)} + m_{(2,2)}) \pm \sqrt{(m_{(1,1)} + m_{(2,2)})^2 - (4)(1)(m_{(1,1)}m_{(2,2)}-m_{(1,2)}m_{(2,1)})}}{2}
$$

With all known eigenvalues now solved for, the eigenvectors can be solved with the equation...

$$
\vec{e}(M - \lambda I_{2^2}) = 0
$$
- Solve for the inner and then apply the result to the 