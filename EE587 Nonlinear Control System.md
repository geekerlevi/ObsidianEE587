## Class 1
<u>Nonlinear Dynamical Systems</u>
Ex. $F(x)=0, x \in \mathbf{R}^{n}$
$F(x)=Ax-b$
$F$ is <u>affine</u> in $x$
EE510: conditions on $A$ and $b$
for existence and uniqueness of solution to $Ax=b$
$A \in \mathbf{R}^{n \times n}, b \in \mathbf{R}^{n \times 1}$
$F(x)=Ax$: linear
$F(x)=Ax+b$: affine
$F(x)=x^TAx$: (e.g., nonlinear)
---
Unconstrained optimization
$min_{x} g(x)$ where $g: \mathbf{R}^n \rightarrow \mathbf{R}$
Necessary: $\nabla g(x)=0 \rightarrow F(x)=0$
$g=\frac{1}{2} x^TAx-bx$
$\nabla g=Ax-b$
$F$ nonlinear: in general difficult to solve $F(x)=0$ analytically
Alternative: iterative approach

<u>Gradient Descent</u>
$x^{k+1}=x^k-\alpha^k \nabla g(x^k)$ --- Discrete-time (DT)
where $\alpha^ k$ is step-size
$\frac{x^{k+1}-x^k}{\alpha^k}=-\nabla g(x^k)$
$\frac{dx}{dt}=-\nabla g(x)$             --- Continuous-time (CT)
$\frac{dx}{dt}=-F(x)$
$\dot{x}=-F(x)$
$\implies \frac{x^{k+1}-x^k}{\alpha}=-F(x^k)$
$x^{k+1}=x^k-\alpha F(x^k)$
$x^{k+1}=-\tilde{F}(x^k)$
where $\alpha F(x^k)-x^k=\tilde{F}(x^k)$
meaning $x^{k+1} \neq -\tilde{F}(x^k)$

$\frac{dx}{dt}=f(x)$ where $x \in \mathbf{R}^n$, $t:$ time, $F:\mathbf{R}^n \rightarrow n$
$x=\begin{bmatrix} x_1 \\ ... \\ x_n\end{bmatrix}, \frac{dx}{dt}=\dot{x}=\begin{bmatrix} \dot{x}_1 \\...\\ \dot{x}_n\end{bmatrix}$
$\begin{bmatrix} \dot{x}_1 \\...\\ \dot{x}_n\end{bmatrix}=f\begin{pmatrix}x_1 \\ ... \\ x_n\end{pmatrix}=\begin{bmatrix} f_1(x_1 ... x_n)\\ ... \\ f_n(x_1... x_n)\end{bmatrix} \neq \begin{bmatrix} f_1(x_1) \\ ... \\ f_n(x_n)\end{bmatrix}$

Ex.
![[Pasted image 20260124184337.png]]
$m:$ mass
$u:$ external force
1. $u=0$
$ml \frac{d^2 \theta}{dt^2}+lk \frac{d\theta}{dt}+mg\sin {\theta}=u=0$
$\theta=x_1$
$\dot{\theta}=x_2$
So,
$\dot{\theta}=\dot{x}_1=x_2$
$\ddot{\theta}=\dot{x}_2$

$ml \dot{x}_2+lk x_2+mg \sin{x_1}=0$
$\dot{x}_2=-\frac{k}{m}x_2-\frac{g}{l} \sin{x_1}$
$\dot{x}_1=x_2$

$X=\begin{bmatrix} x_1 \\ x_2\end{bmatrix}$
$f_1(x_1,x_2)=x_2$
$f_2(x_1,x_2)=-\frac{k}{m}x_2-\frac{g}{l} \sin{x_1}$

$X=\begin{bmatrix} x_1 \\ x_2\\ x_3\end{bmatrix}$
$x_3=t$
$\dot{x}_3=1$
$f_1(x_1,x_2,x_3)=x_2$
$f_2(x_1,x_2,x_3)=-\frac{k}{m}x_2-\frac{g}{l} \sin{x_1}$
$f_3(x_1,x_2,x_3)=1$

2. $u=mg\cos{\theta}$
$m l \frac{d^2 \theta}{dt^2}+lk \frac{d\theta}{dt}+mg\sin{\theta}=mg \cos{\theta}$
$m l \frac{d^2 \theta}{dt^2}+lk \frac{d\theta}{dt}+mg (\sin{\theta}-\cos{\theta})=0$
$\dot{x}=f(x)$
$X=\begin{bmatrix} x_1 \\ x_2\end{bmatrix}$
$x_1=\theta$
$x_2=\dot{\theta}$
$f_1(x_1,x_2)=x_2$
$f_2(x_1,x_2)=-\frac{k}{m}x_2-\frac{g}{l} \sin{x_1}+\frac{g}{l} \cos{x_1}$
$\dot{x}=f(x)$: no explicit $u$
$\implies$ autonomous system
Forced system can still be autonomous!
3. $u=mg \cos{\omega t}$
$\dot{x}_1=x_2$
$\dot{x}_2=-\frac{k}{m} x_2 - \frac{g}{l} \sin{x_1}+\frac{g}{l} \cos{\omega t}$
$\dot{x}=f(x)$ --- time-invariant
$\dot{x}=f(x,t)$ --- time-varying
$\dot{x}=f(x,u)$
Define:
$x_3=t$
$\dot{x}_3=1$
$ml \frac{d^2 \theta}{dt^2}+lk \frac{d \theta}{dt}+mg \sin{\theta}=u$
$\theta=x_1$
$\dot{\theta}=x_2$
$\dot{x}_1=x_2=f_1(x_1,x_2,u)$
$\dot{x}_2=-\frac{k}{m}x_2-\frac{g}{m} \sin{x_1}+u=f_2(x_1,x_2,u)$

Specifying initial conditions - linear system
$f: \mathbf{R}^{n} \times \mathbf{R}^{m} \rightarrow \mathbf{R}^n$
where $x \in \mathbf{R}^{n}, u \in \mathbf{R}^{m}$
$\dot{x}=f(x)$
$x(0)=x_0$
$\dot{x}=Ax$
$f: \mathbf{R}^{n} \rightarrow \mathbf{R}^n, x \in \mathbf{R}^n, A \in \mathbf{R}^{n \times n}$

$\dot{x}=f(x,u)$
$x(0)=x_0$
$\dot{x}=Ax+Bu$
$x(0)=x_0$
$f(x,u)=Ax+Bu$
$f: \mathbf{R}^{n} \times \mathbf{R}^{m} \rightarrow \mathbf{R}^n, u \in \mathbf{R}^m, B \in \mathbf{R}^{n \times m}$

$x(t)=e^{At}x(0)+\int_{0}^{t} e^{A(t-\tau)}Bu(\tau)d\tau$
where $e^{At}x(0)$ is the I.C., $\int_{0}^{t} e^{A(t-\tau)}Bu(\tau)d\tau$ is the input

---
$f(x)$ linear if:
-$f(0)=0$
-$f(\alpha x)= \alpha f(x)$
-$f(x_1+x_2)=f(x_1)+f(x_2)$

$\dot{x}=-\alpha \frac{x^2}{k}=f(x)$
$x^2=z$
$f(z)=-\alpha \frac{z}{k}$
Differentiate: $2x \dot{x}=\dot{z}$
$\dot{x}=\frac{\dot{z}}{2x}$
$\frac{\dot{z}}{2x}=-\alpha \frac{z}{k}$
$\dot{x}=-\alpha \frac{z}{k}$
$\dot{z}=-2\alpha \frac{xz}{k}$

$\dot{x}=\alpha (1-\frac{x}{k})x=f(x)$ with $\alpha>0, k>0$
$f(x)=0$
$\alpha(1-\frac{x}{k})x=0$
$x=0$ and $x=k$
$x(0)=0$ or $k$ equilibrium points
![[Pasted image 20260124222814.png]]
<u>Equilibrium points</u>:
$\dot{x}=f(x)$ --- $(\ast)$
Equilibrium points are <u>constant trajectories</u>
i.e., solution to $(\ast)$ that does not change with time
![[Pasted image 20260124223145.png]]
$f(x^{\ast})=0 \implies x^{\ast}$ is an equilibrium point

---
$f(x)=Ax$
$Ax=0$
-Always has equilibrium $x^{\ast}=0$
-Could have infinitely many equilibriums, $A$ is not inventible
$A=\begin{bmatrix}1 & -1 \\ 1&-1\end{bmatrix}$
$\dot{x}=-x$
$x=0$ only equilibrium point

$\dot{x}=-x+t$
$f(x,t) \implies x=t$

$\dot{x}=-tx$
$x=0$ is the only equilibrium point

---
Suppose $\dot{x}=f(x)$ has unique equilibrium of $x^{\ast}=k$
$\dot{x}=x-k$
$\tilde{x}=x-k$
$\dot{\tilde{x}}=\dot{x}$
$\dot{\tilde{x}}=f(x)$
$\dot{\tilde{x}}=f(\tilde{x}+k)$

## Week 2
<u>Linearization</u>
$\dot{x}=f(x)$ time-invariant
$\bar{x}$: a solution (feasible trajectory)
$x(t)=\bar{x}(t)+\tilde{x}(t)$
where $\bar{x}(t)$ is a given trajectory (e.g., an equilibrium)
$\tilde{x}(t)=x(t)-\bar{x}(t)$
where $\tilde{x}(t)$ is the perturbation around $\bar{x}$
Take derivative:
$\dot{x}(t)=\dot{\bar{x}}+\dot{\tilde{x}}(t)$
$\dot{\tilde{x}}(t)=\dot{x}(t)-\dot{\bar{x}}(t)$
==$\dot{\tilde{x}}(t)=f(\bar{x}+\tilde{x})-f(\bar{x})$== --- dynamics of the perturbed variable
Because $\dot{x}(t)$ is a solution
$\implies \dot{\bar{x}}(t)=f(x(t))$
Recall $f$ is time invariant

- $\bar{x}$ is an equilibrium
$\dot{\tilde{x}}(t)=f(\bar{x}+\tilde{x})-f(\bar{x})$
where $f(\bar{x})=0$
Time-invariant
- $\bar{x}$ is not an equilibrium
$\dot{\tilde{x}}=f(\bar{x}(t)+\tilde{x})-f(\bar{x}(t))$
Time-varying
No approximation
$\dot{\tilde{x}}=f(\bar{x}+\tilde{x})-f(\bar{x})$
For sufficient small $\tilde{x}$
$f(\bar{x}+\tilde{x})-f(\bar{x}) \approx \frac{\partial f}{\partial x} |_{x=\bar{x}} \cdot \tilde{x}$ ---Taylor Approximation
![[Pasted image 20260124224600.png]]
Approximate dynamics for the perturbed variable:
$\dot{\tilde{x}}=\frac{\partial f}{\partial x} |_{x=\bar{x}} \cdot \tilde{x}$
where $\frac{\partial f}{\partial x} |_{x=\bar{x}}=A$
$\dot{\tilde{x}}=A\tilde{x}$
$\implies$ ==$\tilde{x}(t)=e^{At} \tilde{x}(0)$== --- General solution
$e^{At}=I+At+ \frac{A^2 t^2}{2!} + \frac{A^3 t^3}{3!}+...$

Example. $\dot{x}=\alpha (1-\frac{x}{k}) x$
where $\alpha (1-\frac{x}{k}) x=f(x)$
$\frac{\partial f}{\partial x}=\frac{\partial}{\partial x} [\alpha (1-\frac{x}{k}) x]$
$\frac{\partial f}{\partial x}=\alpha (1-\frac{2x}{k})$
- $\bar{x}=0$
$\frac{\partial f}{\partial x} |_{x=\bar{x}=0}=\alpha$
==$\dot{\tilde{x}}=\alpha \tilde{x}$==
$\tilde{x}(t)=\tilde{x}(0) e^{\alpha t}$
$x=\tilde{x}+\bar{x}=\tilde{x}+0=\tilde{x}$
$x(t)=x(0)e^{\alpha t}$

- $\bar{x}=k$
$\frac{\partial f}{\partial x} |_{x=\bar{x}=k}=-\alpha$
$\dot{\tilde{x}}=-\alpha \tilde{x}$
$\tilde{x}(t)=e^{-\alpha \tilde{x}(t)}$
$x=\tilde{x}+\bar{x}$
$\tilde{x}=x-k$
$x(t)-k=(x(0)-k) e^{-\alpha t}$
$x(t)=k(1-e^{-\alpha t})+x(0) e^{-\alpha t}$
$x(t)=k+(x(0)-k)e^{-\alpha t}$

---
- Small perturbations around $\bar{x}=0$ are going to grow 
$\bar{x}=0$ is unstable
- Small perturbations around $\bar{x}=k$ decay with time
$\bar{x}=k$ is locally asymptotically stable

---
Ex.
1. $\dot{x}=-x^3$
$f(x)=-x^3$
$f(x)=0 \implies x=0$
![[Pasted image 20260124230141.png]]
2. $\dot{x}=x^3$
$f(x)=x^3$
$f(x)=0 \implies x=0$
![[Pasted image 20260124230207.png]]

- $f=-x^3$
$\frac{\partial f}{\partial x}=-3x^2$
$\frac{\partial f}{\partial x} |_{x=0}=0$
- $f=x^3$
$\frac{\partial f}{\partial x}=3x^2$
$\frac{\partial f}{\partial x} |_{x=0}=0$

$\dot{\tilde{x}}= 0 \cdot \tilde{x}=0$ --- both systems
$\tilde{x}(t)=\tilde{x}(0)$
$x=\tilde{x}+\bar{x}=\tilde{x}+0=\tilde{x}$
$x(t)=x(0)$

$\dot{x}_1=f_1(x)=f_1(x_1,x_2)$
$\dot{x}_2=f_2(x)=f_2(x_1,x_2)$
$\frac{\partial f}{\partial x}=\begin{bmatrix} \frac{\partial f_1}{\partial x_1} & \frac{\partial f_1}{\partial x_2} \\ \frac{\partial f_2}{\partial x_1}  & \frac{\partial f_2}{\partial x_2} \end{bmatrix}$
$x(t)=e^{At} x(0)$

Ex1. 
![[Pasted image 20260124230620.png]]
$m \ddot{y}=u$
$y=x_1$
$\dot{y}=\dot{x}_1=x_2$
$\dot{x}_1=x_2$
$\dot{x}_2=\frac{u}{m}$
$\begin{bmatrix} \dot{x}_1 \\ \dot{x}_2 \end{bmatrix} = \begin{bmatrix} 0 & 1 \\ 0 & 0\end{bmatrix} \begin{bmatrix} x_1 \\ x_2\end{bmatrix} + \begin{bmatrix} 0 \\ \frac{1}{m}\end{bmatrix} u$
where $A=\begin{bmatrix} 0 & 1 \\ 0 & 0\end{bmatrix}, B=\begin{bmatrix} 0 \\ \frac{1}{m}\end{bmatrix}$
$\dot{x}=Ax+Bu$
unforced system: $\dot{x}=Ax=f(x)=\begin{bmatrix} 0 & 1 \\ 0 & 0\end{bmatrix}x$
$x(t)=e^{At} x(0)$
$e^{At}=I+At+\frac{A^2 t^2}{2!}+...$
$\begin{bmatrix} 0 & 1 \\ 0 & 0\end{bmatrix} \begin{bmatrix} x_1 \\ x_2\end{bmatrix}=0$
$\implies x_2=0, x_1 \in \mathbf{R}$
$X=0: x_1=0, x_2=0$
$x_1=1, x_2=0$ (perturbation)
$A^2=\begin{bmatrix} 0 & 1 \\ 0 & 0\end{bmatrix}\begin{bmatrix} 0 & 1 \\ 0 & 0\end{bmatrix}=\begin{bmatrix} 0 & 0 \\ 0 & 0\end{bmatrix}$
$e^{At}=I+At=\begin{bmatrix} 1& 0 \\ 0 & 1\end{bmatrix}+\begin{bmatrix} 0 & 1 \\ 0 & 0\end{bmatrix}t=\begin{bmatrix} 1 & t \\ 0 & 1\end{bmatrix}$
$\begin{bmatrix} x_1(t) \\ x_2(t)\end{bmatrix}= \begin{bmatrix} 1 & t \\ 0 & 1\end{bmatrix}\begin{bmatrix} x_1(0) \\ x_2(0)\end{bmatrix}$
$x_2(t)=x_2(0)$
$x_1(t)=x_1(0)+t x_2(0)$
$A=\begin{bmatrix} 0 & 1 \\ 0 & 0\end{bmatrix}$
$det(A-\lambda I)=det \begin{pmatrix} -\lambda & 1 \\ 0 & -\lambda \end{pmatrix}=\lambda^2=0$
$\implies \lambda=0$

Ex2.
![[Pasted image 20260124231553.png]]
$m \ddot{y}+ky=u$
$A=\begin{bmatrix} 0 & 1 \\ -\frac{k}{m} & 0\end{bmatrix}, B=\begin{bmatrix} 0 \\ \frac{1}{m}\end{bmatrix}$
$det(A-\lambda I)=det \begin{pmatrix} -\lambda & 1 \\ -\frac{k}{m} & -\lambda \end{pmatrix}=\lambda^2+\frac{k}{m}=0$
$\implies \lambda = \pm \sqrt{\frac{k}{m}} j$

Ex3.
![[Pasted image 20260124231818.png]]
$m \ddot{y}+c\dot{y}+ky=u$
$y=x_1$
$x_2=\dot{x}_1$
$\dot{x}_2=\frac{1}{m} (u-kx_1-cx_2)$
$\begin{bmatrix} \dot{x}_1 \\ \dot{x}_2 \end{bmatrix} = \begin{bmatrix} 0 & 1 \\ -\frac{k}{m} & -\frac{c}{m}\end{bmatrix} \begin{bmatrix} x_1 \\ x_2\end{bmatrix} + \begin{bmatrix} 0 \\ \frac{1}{m}\end{bmatrix} u$
$A=\begin{bmatrix} 0 & 1 \\ -\frac{k}{m} & -\frac{c}{m}\end{bmatrix}, B=\begin{bmatrix} 0 \\ \frac{1}{m}\end{bmatrix}$
$det(A-\lambda I)=det \begin{pmatrix} -\lambda & 1 \\ -\frac{k}{m} & -\frac{c}{m}-\lambda \end{pmatrix}=\lambda^2+\frac{c}{m}\lambda+\frac{k}{m}=0$
$\implies \lambda=\frac{-\frac{c}{m}+\sqrt{\frac{c^2}{m^2}-4\frac{k}{m} }}{2}$
$\lambda=\frac{-c+\sqrt{c^2-4km }}{2m}$
$c > 2 \sqrt{mk}$
$\lambda_{1,2} <0$
$Re(\lambda_{1,2})<0$

---
![[Pasted image 20260124232434.png]]
All e-values strictly in the left half plane $\implies x=0$ is stable
("every trajectory converges to $x=0$")
At least one-value in the right half plane $\implies x=0$ is not stable
("some trajectories grow unbounded")

2D systems
characteristic polynomial: $\lambda^2+a_1 \lambda+a_0=0$
$a_1>0, a_0>0 \implies$ stability

\
Range of phenomena for $\dot{x}=f(x)$ (nonlinear)
1. Multiple "isolated" equilibrium points
2. Finite escape time
3. Limit cycles
4. Chaos

Ex1. 
![[Pasted image 20260125012322.png]]
not an isolated equilibrium
- If $\exists$ a neighborhood around $\bar{x}$ which does not contain any other equilibrium
$\implies \bar{x}$ is an isolated equilibrium
- All neighborhoods around $\bar{x}$ contain at least one other equilibrium
$\implies \bar{x}$ is not an isolated equilibrium

## Class3
$\dot{x}=f(x)$
Definition: $x(t)$ is a periodic orbit if $\exists T>0$ such that $x(t+T)=x(t), \forall t$
\
<u>Linear systems</u>:
<u>1-Dimensional</u>: 
$\dot{x}=ax$
No periodic orbits $\forall a$
![[Pasted image 20260125135808.png]]
$f(x)$ along $x(t)$ is monotonic
\
<u>2-Dimensional</u>:
$\dot{x}=\begin{bmatrix} 0 & -\beta \\ \beta & 0\end{bmatrix} x$
$\lambda_{1,2}=\pm j \beta$
$\dot{x}_1=-\beta x_2$
$\dot{x}_2=\beta x_1$
$\ddot{x}_1=-\beta \dot{x}_2$
$\ddot{x}_2=\beta \dot{x}_1$
![[Pasted image 20260125140036.png]]
$\frac{d}{dt} (x_1^2+x_2^2)=2x_1 \dot{x}_1+2x_2 \dot{x}_2$
$=2 x_1 (-\beta x_2)+2x_2(\beta x_1)$
$=0$
an "isolated" periodic orbit cannot occur in linear system
limit cycle = "isolated" periodic orbit

---
$\dot{x}=Ax$
<u>2-Dimensional</u>:
$z=T^{-1}x$
$\implies \dot{z}=T^{-1} \dot{x}=T^{-1} Ax=T^{-1} A Tz$
For proper choice of $T$
$\dot{z}=\begin{bmatrix} \lambda_1 & 0 \\ 0 & \lambda_2\end{bmatrix} z$
or
$\dot{z}=\begin{bmatrix} \lambda_1 & 1 \\ 0 & \lambda_2\end{bmatrix} z$
or 
$\dot{z}=\begin{bmatrix} \alpha & \beta \\ -\beta & \alpha\end{bmatrix} z$
where $\begin{bmatrix} \lambda_1 & 0 \\ 0 & \lambda_2\end{bmatrix}, \begin{bmatrix} \lambda_1 & 1 \\ 0 & \lambda_2\end{bmatrix}, \begin{bmatrix} \alpha & \beta \\ -\beta & \alpha\end{bmatrix}$ are $T^{-1}AT$
Real $\lambda's$
![[Pasted image 20260125174557.png]]
$\lambda_1 < \lambda_2 <0$
$\dot{z}=\begin{bmatrix} \lambda_1 & 0 \\ 0 & \lambda_2\end{bmatrix} z$
$\dot{z}_1 =\lambda_1 z_1$
$\dot{z}_2=\lambda_2 z_2$
$z_1=e^{\lambda_1} z_1 (0)$
$z_2=e^{\lambda_2}z_2(0)$
![[Pasted image 20260125174712.png]]
$\lambda_1 > \lambda_2>0$
![[Pasted image 20260125174727.png]]
$\lambda_2< 0 < \lambda_1$

<u>Complex eigenvalues</u>
$\dot{z}=\begin{bmatrix} \alpha & \beta \\ -\beta & \alpha\end{bmatrix} z$
$\alpha=0$
=="marginally stable"==
![[Pasted image 20260125174845.png]]
$\alpha>0$
$\frac{d}{dt} (z_1^2 + z_2^2)=2z_1 \dot{z}_1+2 z_2 \dot{z}_2$
$=2z_1[\alpha z_1 -\beta z_2]+2 z_2 [\beta z_1 + \alpha z_2]$
$=2\alpha(z_1^2+z_2^2)$
![[Pasted image 20260125174959.png]]
$\alpha<0$
![[Pasted image 20260125175007.png]]

---
$\dot{x}=Ax, A \in \mathbf{R}^{n \times n}$
$Re(\lambda_i)<0, \forall i \implies$ stable equilibrium
$Re(\lambda_i)>0$ for at least one $i \implies$ unstable equilibrium
$Re(\lambda_i) \leq 0, \forall i$ and no repeated eigenvalues on the $j \omega$ axis  $\implies$ "marginally stable"

Ex. $\dot{z}=\begin{bmatrix} 0 & 1 \\ 0 & 0 \end{bmatrix} \begin{bmatrix} z_1 \\ z_2\end{bmatrix}$
$\lambda_{1,2}=0$ "unstable system"
$\dot{z}_1=z_2$
$\dot{z}_2=0$
$z_1(t)=z_2(0)t+z_1(0)$
$z_2(t)=z_2(0)$

---
<u>Hartman–Grobman Theorem</u>
Provides basic for qualitative comparison between $\dot{x}=f(x)$ and $\dot{x}=\frac{\partial f}{\partial x}|_{x=x^{\ast}} (x-x^{\ast})$
Theorem: If $x^{\ast}$ is a hyperbolic (i.e., no eigenvalue on the imaginary axis) equilibrium
Then there exists a ==homeomorphism==
$z=h(x)$ defined in a neighborhood of $x^{\ast}$ that maps trajectories of $\dot{x}=f(x)$ to those of $\dot{z}=Az, A=\frac{\partial f}{\partial x}|_{x=x^{\ast}}$
Homeomorphism: a continuous map with a continuous inverse 
$z=h(x)$ is continuous at $x$ if $\forall \epsilon >0 \exists \delta>0$ such that $||\tilde{x}-x||< \delta \implies ||\tilde{z}-z||<\epsilon$
$\tilde{z}=h(\tilde{x})$
![[Pasted image 20260125175817.png]]
$||\tilde{x}-1|| \leq 0.5 \rightarrow ||\tilde{z}-1|| \leq 0.5$
where $x=1, z=1, \epsilon=0.5, \delta=0.5$

![[Pasted image 20260125175911.png]]
$\epsilon=0.5$ (user specified)
Pick $\delta$
$||\tilde{x}-1|| < \delta \implies ||\tilde{z}-1|| <0.5$

$\dot{z}=Az$
![[Pasted image 20260125180102.png]]
$z=h(x)$
![[Pasted image 20260125180116.png]]
saddle point

$\dot{x}=f(x)$
![[Pasted image 20260125180136.png]]

![[Pasted image 20260125180141.png]]

Ex. necessity of hyperbolicity condition
$\dot{x}_1=-x_2+a x_1 (x_1^2+x_2^2)$
$\dot{x}_2=x_1+ax_2 (x_1^2+x_2^2)$
$x_1=x_2=0$
$\frac{\partial f_1}{\partial x_1}=3ax_1^2 |_{x=x^{\ast}}=0$
$\frac{\partial f_1}{\partial x_2}=2ax_1x_2-1|_{x=x^{\ast}}=-1$
$\frac{\partial f_2}{\partial x_1}=2ax_1x_2+1 |_{x=x^{\ast}}=1$
$\frac{\partial f_2}{\partial x_2}=3ax_2^2 |_{x=x^{\ast}}=0$
$A=\begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix}$
$\lambda^2+1=0$
$\lambda= \pm j$
$\dot{z}=Ax$
![[Pasted image 20260125180602.png]]
$z(nt)-z(\epsilon)$ is very small
$x(nt)-x(\epsilon)$

$\dot{x}=f(x)$
$r=x_1^2+x_2^2$
$\theta=\tan^{-1}(\frac{x_2}{x_1})$
$\dot{r}=ar^3$
$\dot{\theta}=1$
![[Pasted image 20260125180724.png]]
$\dot{x}=f(x)$
- $\dot{x}=0$ is locally asymptotically stable
- $\dot{x}=0$ is unstable
$\exists x_0$ such that $x(t)$ grows unbounded

$\dot{z}=Az$
$A=\frac{\partial f}{\partial x}|_{x=\dot{x}=0}$
- $Re(\lambda_i) <0, \forall i$, locally asymptotically stable
- $Re(\lambda_i) >0$ for some i, unstable

This is the end of linearization

---
1 Dimensional - Finite escape time
$\dot{x}=x^2, x=0$ is the equilibrium point
$\int_{x_0}^{x} \frac{dx}{x^2}=\int_{t_0}^{t}dt$
$-\frac{1}{x} |_{x_0}^{x}=t-t_0$
$\frac{1}{x_0}-\frac{1}{x} = t-t_0$
$\implies \frac{1}{x}= \frac{1}{x_0} - (t-t_0)$
$\frac{1}{x}=\frac{1-x_0(t-t_0)}{x_0}$
$x=\frac{x_0}{1-x_0(t-t_0)}$
$t_0=0, x(t)=\frac{1}{\frac{1}{x_0}-t}$
$t \rightarrow \frac{1}{x_0}$
$\implies x(t) \rightarrow \infty$

Ex. 
$\dot{x}=x^2+1, x\in \mathbf{R}$
No equilibrium

## Class 4
<u>Periodic orbits in the plane</u>

<u>Bendixson's Theorem</u>:
Time-invariant planer system:
$\dot{x}_1=f_1(x_1,x_2)$
$\dot{x}_2=f_2(x_1,x_2)$
$\nabla f(x)=\frac{\partial f_1}{\partial x_1}+\frac{\partial f_2}{\partial x_2}$
If $\nabla f(x)$ is not identically zero and does not change sign in a simply connected region$D$
then there are no periodic orbits exist that lie entirely in $D$

![[Pasted image 20260126111211.png]]
simply connected but not convex

For a linear system
$f(x_1,x_2)=A \begin{bmatrix} x_1 \\ x_2\end{bmatrix}$
$A=\begin{bmatrix} \frac{\partial f_1}{\partial x_1} & \frac{\partial f_1}{\partial x_2}\\ \frac{\partial f_2}{\partial x_1} & \frac{\partial f_2}{\partial x_2}\end{bmatrix}$
$\nabla f(x)=\frac{\partial f_1}{\partial x_1}+\frac{\partial f_2}{\partial x_2}= Tr(A)$
For a periodic orbit to exist in a linear system, it is necessary for $Tr(A)=0$
Periodic orbit:
$\dot{x}=\begin{bmatrix} 0 & -\beta \\ \beta & 0 \end{bmatrix} x$

$\dot{x}=\begin{bmatrix} \alpha & -\beta \\ \beta & \alpha \end{bmatrix} x, \alpha \neq 0$
$Tr(A)=2 \alpha$

$\dot{x}=\begin{bmatrix} 0 & 0 \\ 0 & 0 \end{bmatrix} x$
$Tr(A)=0$

Ex.
$\delta>0$
$\dot{x}_1= x_2$
$\dot{x}_2=-\delta x_2+x_1-x_1^3+x_1^2x_2$
$\nabla f(x)=\frac{\partial f_1}{\partial x_1}+\frac{\partial f_2}{\partial x_2}$
$=0+(-\delta+x_1^2)$
$=x_1^2-\delta$
![[Pasted image 20260126111707.png]]

---
<u>Poincare-Bendixson Theorem</u>
<u>Invariant set</u>
A set $M \subset \mathbf{R}^{n}$ is (positively) invariant, if for each initial condition in $M$, the trajectory remains in $M, \forall t \geq 0$
![[Pasted image 20260126111915.png]]

![[Pasted image 20260126111928.png]]
$f(x) \cdot n(x) \leq 0, \forall x$ on the boundary of $M \implies M$ is positively invariant

![[Pasted image 20260126112012.png]]
$f(x) \cdot n(x) <0, \forall x$ on the boundary of this circle $\implies$ circle is positively invariant
under-approximation of the maximal positively invariant set

Ex. Predator-Prey model, $a,b,c,d >0$
$\dot{x}=(a-by)x$ --- Prey (exponential grouth when $y=0$)
$\dot{y}=(cx-d)y$
![[Pasted image 20260126112225.png]]
$f \cdot n \leq 0$
$(cx-d)y (-1) \leq 0$ for $y=0$
$=0$

Ex.
$\dot{x}_1= x_1+x_2-x_1 (x_1^2+x_2^2)$
$\dot{x}_2=-2x_1+x_2-x_2(x_1^2+x_2^2)$
$\{x: x_1^2+x_2^2 \leq r\}$ is positively invariant for sufficiently large $r$
![[Pasted image 20260126112438.png]]

$f(x) \cdot n(x)= x_1^2+x_1x_2-x_1^2(x_1^2+x_2^2)-2x_1x_2+x_2^2-x_2^2(x_1^2+x_2^2)$
$=x_1^2+x_2^2-(x_1^2+x_2^2)^2-x_1x_2$
$=r^2-r^4-x_1x_2$
$(x_1+x_2)^2 \geq 0$
$x_1^2+x_2^2+2x_1x_2 \geq 0$
$-x_1x_2 \leq \frac{x_1^2+x_2^2}{2}$
$-x_1x_2 \leq \frac{r^2}{2}$
$f(x) \cdot n(x)=r^2-r^4-x_1x_2$
$\leq r^2-r^4+\frac{r^2}{2}$
$=\frac{3}{2}r^2-r^4$
$=r^2(\frac{3}{2}-r^2)$
$\leq 0$ if $r \geq \sqrt{\frac{3}{2}}$

---
<u>Poincare-Bendixson Theorem</u>
Suppose $M$ is compact (closed and bounded), and positively invariant for a planar time invariant system $\dot{x}=f(x), x \in \mathbf{R}^2$
If $M$ contains no equilibrium points, then it contains a periodic orbit

Ex. 
$A=\begin{bmatrix}0 & -1 \\ 1 & 0 \end{bmatrix}$
$\dot{x}_1=-x_2$
$\dot{x}_2=x_1$
![[Pasted image 20260126112939.png]]
![[Pasted image 20260126112950.png]]
$M$ is compact and positively invariant and does not include equilibrium
$\implies \exists$ a periodic orbit in $M$

---
<u>Bifurcations</u> 
A bifurcation is an abrupt change in qualitative behavior as a parameter is varied.
Example: equilibria or limit cycles appearing/ disappearing becoming stable/ unstable
- Transition: multiple equilibria $\leftrightarrow$ no equilibrium
Fold bifurcation, "blue-sky" bifurcation, or "saddle node" bifurcation
$\dot{x}=\mu-x^2=f(x)$
$f(x)=0$ has solution only if $\mu \geq 0$
$\mu<0:$ no equilibrium
$\mu=0:$ one equilibrium
$\mu >0:$ two equilibria
![[Pasted image 20260126113336.png]]
$\dot{x}=\mu-x^2$
$\dot{\tilde{x}}=\frac{\partial f}{\partial x}|_{x=x^{\ast}} (\tilde{x}-x^{\ast})$
$\dot{x}=\sqrt{\mu}$
$\frac{\partial f}{\partial x}= \frac{\partial }{\partial x} (\mu-x^2)$
$=-2x |_{x=\sqrt{\mu}}$
$=-2\sqrt{\mu}$
$\dot{\tilde{x}}=-2\sqrt{\mu} (\tilde{x}-\sqrt{\mu})$
![[Pasted image 20260126113531.png]]
- Trans-critical bifurcation
$\dot{x}=\mu x-x^2=f(x)$
$\mu x-x^2=0$
$\implies x=0$ and $x=\mu$
$\mu<0: x=0$ is stable, $x=\mu$ is stable
$\mu>0:x=0$ is unstable, $x=\mu$ is stable
$\frac{\partial f}{\partial x} |_{x=0}=\mu-2x|_{x=0}=\mu$
$\frac{\partial f}{\partial x} |_{x=\mu}=\mu-2x|_{x=\mu}=-\mu$
![[Pasted image 20260126140202.png]]

- Pitchfork Bifurcation
$\dot{x}=\mu x-x^3$
$\mu x-x^3=0$
$\mu<0: x=0$ always
$\mu \geq0: x=0, x=\pm \sqrt{x}$

|                 | $\mu<0$ | $\mu>0$  |
| --------------- | ------- | -------- |
| $x=0$           | Stable  | Unstable |
| $x=+\sqrt{\mu}$ | N/A     | Stable   |
| $x=-\sqrt{\mu}$ | N/A     | Stable   |

$\frac{\partial f}{\partial x}|_{x=0}=\mu-3x^2 |_{x=0}=\mu$
$\frac{\partial f}{\partial x}|_{x=\sqrt{\mu}}=\mu-3x^2 |_{x=\sqrt{\mu}}=-2\mu$
$\frac{\partial f}{\partial x}|_{x=-\sqrt{\mu}}=\mu-3x^2 |_{x=-\sqrt{\mu}}=-2\mu$
![[Pasted image 20260126140648.png]]
super-critical
$\dot{x}=\mu x+x^3$
![[Pasted image 20260126140707.png]]
subcritical

## Class 5
<u>Two-dimensional bifurcation</u>
Hopf bifurcation:

Ex.
$\dot{x}_1=x_1 (\mu-x_1^2-x_2^2)-x_2$
$\dot{x}_2=x_2(\mu-x_1^2-x_2^2)+x_1$
In polar coordinates
$\dot{r}=\mu r-r^3=f(r)$
$\dot{\theta}=1$

$f(r)=0$
$r(\mu-r^2)=0$
$r=0$ or $\mu-r^2=0$
$\mu<0:$ equilibrium at $x=0$ stable
$\mu>0:$ equilibrium at $x=0$ unstable
        and periodic orbit (limit cycle) at $r=\sqrt{\mu}$ stable
$\dot{r}=\mu r-r^3=f(r)$
$\frac{df}{dr}=\mu-3r^2$
$\frac{df}{dr}|_{r=\sqrt{\mu}}=\mu-3\mu=-2\mu <0$ for $\mu>0$
![[Pasted image 20260204124624.png]]
Super-critical Hopf Bifurcation

Ex.
$\dot{r}=\mu r + r^3 -r^5=f(r)$
$\dot{\theta}=1$
$r=0$ is always a solution to $f(r)=0$
Always an equilibrium at $x=0$
$f(r)=r(\mu+r^2-r^4)$
$r^2=z, z \geq 0$
$\mu+z-z^2=0$
$z=\frac{-1 \pm \sqrt{1+4\mu}}{2\mu}$
- $\mu>0, z=\frac{-1 + \sqrt{1+4\mu}}{2\mu}, r =\sqrt{z}$
- $-\frac{1}{4}<\mu<0, z= \frac{-1 \pm \sqrt{1+4\mu}}{2\mu}, r=\sqrt{z}$
- $\mu<-\frac{1}{4}$ no solution in $z$ and hence $r$
$\mu>0:$ equilibrium of $x=0$ unstable
		and a periodic orbit at $r=\sqrt{z_1}$ stable
$-\frac{1}{4}<\mu<0:$ equilibrium of $x=0$ stable 
		and two periodic orbit at $r=\sqrt{z_2}, z_2<z_3$ unstable
							$r=\sqrt{z_3}$ stable
$\mu<-\frac{1}{4}:$ equilibrium stable
![[Pasted image 20260204131536.png]]
sub-critical Hopf bifurcation

<u>Index Theory (planar systems)</u>
![[Pasted image 20260204131618.png]]
Index: The index of a closed curve is $k$ if when traversing the curve in one direction, $f(x)$ rotates by $2 \pi k$ in the same direction 
For any closed orbit, index $=+1$

Node (stable/ unstable)
![[Pasted image 20260204131725.png]]
index$=+1$
![[Pasted image 20260204131735.png]]

Unstable node
![[Pasted image 20260204131750.png]]
index$=+1$

Focus, center
index$=+1$

---

Saddle-point
![[Pasted image 20260204131826.png]]
![[Pasted image 20260204131831.png]]
index$=-1$

No equilibrium inside the closed curve
![[Pasted image 20260204131856.png]]
index$=0$
![[Pasted image 20260204131922.png]]
![[Pasted image 20260204131930.png]]
index$=2$
![[Pasted image 20260204131941.png]]
index$=0$
Theorem: The index of a local curve is equal to the sum of indices of the equilibria inside
Collaroy: Inside any periodic orbits, there must be at least one equilibrium and indices of the equilibrium must add up to $+1$

Recall example
$\dot{x}_1=x_2=f_1(x_1,x_2)$
$\dot{x}_2=-\delta x_2+x_1-x_1^3+x_1^2 x_2=f_2(x_1,x_2), \delta>0$
At equilibrium $x_2=0$
$0+x_1-x_1^3=0$
$x_1=0, \pm1$
Three equilibrium: $(0,0)(1,0)(-1,0)$
$\frac{\partial f}{\partial x}=\begin{bmatrix} \frac{\partial f_1}{\partial x_1} & \frac{\partial f_1}{\partial x_2} \\ \frac{\partial f_2}{\partial x_1} & \frac{\partial f_2}{\partial x_2}\end{bmatrix}=\begin{bmatrix} 0 & 1 \\ 1-3x_1^2+2x_1x_2 & -\delta+x_1^2\end{bmatrix}$
$\frac{\partial f}{\partial x}|_{(0,0)}=\begin{bmatrix} 0 & 1 \\ 1 & -\delta\end{bmatrix}$
$\implies$ e-values are real and have opposite signs
$\implies$ saddle
$\frac{\partial f}{\partial x}|_{(1,0)(-1,0)}=\begin{bmatrix} 0 & 1 \\ -2 & 1-\delta\end{bmatrix}$
$\implies$ e-values are real and the same sign
			or are complex
$\implies$ node, focus, or center
![[Pasted image 20260204152306.png]]
## Class 6
Recall PB Theorem: (planar)
If $\exists$ positively invariant compact set $M$ with no equilibrium
then $\exists$ a periodic orbit in $M$
![[Pasted image 20260204152426.png]]

---
General form of PB theorem:
For (time invariant, planar system), bounded trajectories converge to equilibria, periodic orbits or union of equilibria connected by trajectories

Ex. equilibria connected by trajectories
![[Pasted image 20260204152855.png]]
No "chaos" in 2D time-invariant continuous time system

Discrete Time: $x_{t+1}=f(x_t)$
Continuous Time: $\dot{x}=f(x)$
"fixed points": $f(x)=x$
<u>Asymptotic Stability Criterion</u>
$x_{t+1}=Ax_t$
$A=\frac{\partial f}{\partial x}|_{x=0}$
$|\lambda_i(A)<1|, \forall i$
$\lambda_i=a_i+jb_i$
$|\lambda_i|=\sqrt{a_i^2+b_i^2}$
![[Pasted image 20260204155903.png]]
If $|\lambda_i(A)|>1$ for some $i \implies x=0$ is unstable

<u>Cobweb Diagram</u>
$\dot{x}=sinx$
![[Pasted image 20260204160211.png]]
$x_{t+1}=sin(x_t)$
fixed point: $sin x= x$
$\implies x=0$
![[Pasted image 20260204160226.png]]

![[Pasted image 20260204160237.png]]
$f(x)=sinx$
$\frac{\partial f}{\partial x}=cosx$
$\frac{\partial f}{\partial x}|_{x=0}=cos0=1$
$x_1=f(x_0)$
$x_2=f(x_1)$
Linearization cannot evaluate stability $x=0$ for $x_{t+1}=sin(xt)$

DT: Periodic orbit has period $T$
if $x_{t+T}=x_t, \forall t$

$x_{t+1}=f(x_t)$
$x_6=x_4=x_2=x_0$
$x_7=x_5=x_3=x_1=f(x_0)$
$x_2=f(x_1)$
$x_2=f(f(x_0))$
$x_1=f(f(x_1))$

Claim: if $x_0$ is a fixed point of $fof$
$x_1$ is a fixed point of $fof$
![[Pasted image 20260204184137.png]]
Ex. $x_{t+1}=r(1-x_t)x_t$
logistic growth model
$max (1-x)x=\frac{1}{4}$ at $x=\frac{1}{2}$
$x \in [0,1]$
$x_0 \in [0,1] \implies x_t \in [0,1], \forall t$
Fixed points: $f(x)=r(1-x)x$
$f(x)=x$
$r(1-x)x=x$
$x=0$,  $r(1-x)=1$
$x=1-\frac{1}{r}, r>1$
![[Pasted image 20260204184755.png]]
![[Pasted image 20260204184809.png]]
$\frac{df}{dx}=\frac{d}{dx}r(1-x)x=r(1-2x)$
$\frac{df}{dx}|_{x=0}=r$
$\frac{df}{dx}|_{x=1-\frac{1}{r}}=r[1-2(1-\frac{1}{r})]=r[-1+\frac{2}{r}]=-r+2$

---
$fof(x)=f(rx(1-x))$
let $y=rx(1-x)$
$fof(x)=ry(1-y)$
$=rrx(1-x)[1-rx(1-x)]$
$=r^2x(1-x)[1-rx+rx^2]$
At $r=3$
![[Pasted image 20260204185055.png]]
Periodic orbit: $p \leftrightarrow q$

$r=3:$ period-2 cycle born
$r=3.34494:$ period-4 cycle born
$r=3.544:$ period-8 cycle born
$...$
$r_{\infty}=3.5699:$ chaotic behavior
$...$
$r=3.83:$come out of chaotic behavior

Ex.
$\dot{x}_1=x_1x_2=f_1(x_1,x_2)$
$\dot{x}_2=-x_2-x_1^2=f_2(x_1,x_2)$
$\frac{\partial f}{\partial x}=\begin{bmatrix}x_2 & x_1 \\ -2x_1 & -1\end{bmatrix}$

## Class 7
Ex.
$\dot{x}=ax^2=f(x)$
$\frac{\partial f}{\partial x}|_{x=0}=2ax|_{x=0}=0$

Ex.
$\dot{x}=ax^3$
$\dot{y}=-y$

Ex.
$\dot{x}_1=x_1x_2=f_1(x_1,x_2)$
$\dot{x}_2=-x_2-x_1^2=f_2(x_1,x_2)$
$\frac{\partial f}{\partial x}=\begin{bmatrix}x_2 & x_1 \\ -2x_1 & -1\end{bmatrix}$
$\frac{\partial f}{\partial x}|_{x=0}=\begin{bmatrix}0 & 0 \\0 & -1\end{bmatrix}$
$\lambda=0,-1$

<u>Center Manifold Theorem</u>
When the Jacobian has at least one eigenvalues on the $j \omega$ axis
<u>2D</u>
$\lambda_1=0, \lambda_2<0$
$\dot{x}_1=f_1(x_1,x_2)$
$\dot{x}_2=f_2(x_1,x_2)$
$A=\frac{\partial f}{\partial x}|_{x=0}$
$\dot{x}=Ax+(f(x)-Ax)$
Suppose $A=\begin{bmatrix} \lambda_1 & 0 \\ 0 & \lambda_2\end{bmatrix}$
$X=\begin{bmatrix} y \\ z \end{bmatrix}$
$\dot{y}=\lambda_1 y + f_1(y,z)-\lambda_1y$
where $g_1(y,z)= f_1(y,z)-\lambda_1y$
$\dot{z}=\lambda_2 z+ f_2(y,z)-\lambda_2 z$
where $g_2(y,z)=f_2(y,z)-\lambda_2 z$
$\dot{y}=\lambda_1 y +g_1(y,z)$
$\dot{z}=\lambda_2 z+g_2(y,z)$
$g_i(0,0)=0, i=1,2$
$\frac{\partial g_i}{\partial y}(0,0)=0, i=1,2$
$\frac{\partial g_i}{\partial z}(0,0)=0$

Theorem 1: There exists a invariant "manifold" $z=h(y)$ defined in a neighborhood of the origin such that $h(0)=0, \frac{\partial h}{\partial y}(0)=0$
![[Pasted image 20260204211745.png]]

Ex.
$\dot{x}_1=x_1x_2=f_1(x_1,x_2)$
$\dot{x}_2=-x_2-x_1^2=f_2(x_1,x_2)$
$A=\begin{bmatrix} 0 & 0 \\ 0 & -1\end{bmatrix}$
where$\lambda_1=0, \lambda_2=-1$
$y=x_1, z=x_2$
$\begin{bmatrix} y \\ z\end{bmatrix} = I \begin{bmatrix} x_1 \\ x_2\end{bmatrix}$
$g_1(y,z)=f_1(y,z)-A_1y$
$=yz-(0)y$
$=yz$
$g_2(y,z)=f_2(y,z)-A_2y$
$=-z-y^2+z$
$=-y^2$
$\dot{y}=0+yz$
where $yz=g_1$
$\dot{z}=-z-y^2$
where $-y^2=g_2$
Theorem: $\implies \exists$ invariant manifold $z=h(y)$ with $h(0)=0, \frac{\partial h}{\partial y}(0)=0$
Theorem2: If $y=0$ is asymptotically stable (resp. unstable) for the "reduced" system
		then $x=0$ is asymptotically stable (resp. unstable) for the full system $\dot{x}=f(x)$

Q1: How to find $h$?
Q2: "reduced" system
Q3: stability of "reduced" system (nonlinear)

Q1: "invariant" manifold $\implies h$
$w:=z-h(y)$
$z(0)=h(y(0)) \implies z(t)=h(y(t)) ,\forall t$
$w(0)=0 \implies w(t)=0, \forall t$
$w(0)=0 \implies \dot{w}=0, \forall t$
$\dot{w}=\dot{z}-\frac{\partial h}{\partial y}(y) \dot{y}$
$=\lambda_2 z+ g_2(y,z) -\frac{\partial h}{\partial y} (\lambda_1 y + g_1(y,z))=0$ for $z=h(y)$
==$\lambda_2 h(y)+g_2(y,h(y))-\frac{\partial h}{\partial y}g_1(y, h(y))=0$==
In our example, $\lambda_2=-1$
$g_1=yh(y)$
$g_2=y^2$
$-h(y)+y^2-\frac{\partial h}{\partial y}yh(y)=0$
Try: $h(y)=ay^2+O(y^3)$
$\frac{\partial h}{\partial y}=2ay+O(y^2)$
$-ay^2-O(y^3)+y^2-(2ay+O(y^2))y(ay^2+O(y^3))=0$
$-ay^2-O(y^3)+y^2-(2ay^2+O(y^3))(ay^2+O(y^3))=0$
$-ay^2+y^2+O(y^3)=0$
$(1-a)y^2=0$
$a=1$
$h(y)=y^2+O(y^3)$

Q2: 
$\dot{y}=g_1(y,z)$
where $z=h(y)$
$\dot{y}=yh(y)$
$=y(y^2+O(y^3))$
$\dot{y}=y^3+O(y^4)$
"reduced system on the manifold"

Q3:
$\dot{y}=y^3+O(y^4)$
$X=\begin{bmatrix} 0 \\ 0 \end{bmatrix}$ is stable $(a=-1)$ for $\dot{x}=f(x)$

Ex.
$\dot{x}_1=x_2$
$\dot{x}_2=-x_2+x_1^2+x_1x_2$
$\frac{\partial f}{\partial x}|_{x=0} = \begin{bmatrix} 0 & 1 \\ 2x_1+x_2 & -1+x_1\end{bmatrix}=\begin{bmatrix} 0 & 1 \\ 0 & -1\end{bmatrix}=A$
$A-\lambda I =\begin{bmatrix}- \lambda & 1 \\ 0 & -1-\lambda\end{bmatrix}$
$det(A-\lambda I)=0$
$\lambda (\lambda+1)=0$
$\lambda=0, -1$
$\begin{bmatrix} \dot{x}_1 \\ \dot{x}_2\end{bmatrix}=A \begin{bmatrix} x_1 \\ x_2\end{bmatrix}$
$\begin{bmatrix} y \\ z\end{bmatrix}=T \begin{bmatrix} x_1 \\ x_2\end{bmatrix}$
$T$ is invertible
$\begin{bmatrix} \dot{y} \\ \dot{z}\end{bmatrix} = T \begin{bmatrix} \dot{x}_1 \\ \dot{x}_2\end{bmatrix}=TA \begin{bmatrix} x_1 \\ x_2\end{bmatrix}$
$\begin{bmatrix} \dot{y} \\ \dot{z}\end{bmatrix} = TAT^{-1} \begin{bmatrix} y \\ z\end{bmatrix}$
$T=\begin{bmatrix} 1 & 1 \\ 0 & -1\end{bmatrix}$
$TAT^{-1}=\begin{bmatrix} 1 & 1 \\ 0 & -1\end{bmatrix} \begin{bmatrix} 0 & 1 \\ 0 & -1\end{bmatrix} \begin{bmatrix} 1 & 1 \\ 0 & -1\end{bmatrix}$
$=\begin{bmatrix} 1 & 1 \\ 0 & -1\end{bmatrix} \begin{bmatrix} 0 & -1 \\ 0 & 1\end{bmatrix}$
$=\begin{bmatrix} 0 & 0 \\ 0 & -1\end{bmatrix}$
$\begin{bmatrix} y \\ z\end{bmatrix}=\begin{bmatrix} 1 & 1 \\ 0 & -1\end{bmatrix}\begin{bmatrix} x_1 \\ x_2\end{bmatrix}$
$y=x_1+x_2$
$x_1=y+z$
$z=-x_2$
$x_2=-z$
$\dot{y}=\dot{x}_1+\dot{x}_2=x_1^2+x_1x_2$
$=x_1(x_1+x_2)$
$=(y+z)y$
$\dot{z}=\dot{x}_2=x_2-x_1^2-x_1x_2$
$=-z-x_1y$
$=-z-y^2-yz$
$\dot{y}=0+y^2+yz$
$\dot{z}=-z-y^2-yz$
$\lambda_2 h(y)+g_2(y,h(y))-\frac{\partial h}{\partial y}g_1(y, h(y))=0$
$(-1)h(y)+(-y^2-yz)-\frac{\partial f}{\partial y}(y^2+yz)=0$
$-h(y)-(\frac{\partial h}{\partial y}+1)(y^2+yh(y))=0$
Let's try $h(y)=ay^2+O(y^3)$
$-ay^2-O(y^3)-(2ay+O(y^2)+1)(y^2+ay^3+O(y^4))=0$
$-ay^2-O(y^4)=0$
$a=0$
$\implies h(y)=O(y^3)$
"Reduced" system
$\dot{y}=y^2+yz$
$=y^2+yh(y)$
$=y^2+yO(y^3)$
$=y^2+O(y^4)$
$y=0$ is unstable for the reduced system
$\implies X=\begin{bmatrix} 0 \\ 0\end{bmatrix}$ is unstable for $\dot{x}=f(x)$

## Class 8
<u>Center Manifold Theorem</u>
$\dot{x}=f(x)$
$A=\frac{\partial f}{\partial x}|_{x=0}$
$A$ is the Jacobian has $k$ eigenvalues with zero real parts; $n-k$ eigenvalues with negative real parts
$\begin{bmatrix} y \\ z \end{bmatrix}=Tx$
change of variables
$\dot{y}=A_1 y + g_1(y,z)$
where $A_1 \in \mathbf{R}^{k \times k}$
$\dot{z}=A_2 z+g_2(y,z)$
where $A_2 \in \mathbf{R}^{(n-k) \times (n-k)}$
both $A_1, A_2$ are block diagonal
Jordan normal form: $\begin{bmatrix} A_1 & 0 \\ 0& A_2\end{bmatrix}=TAT^{-1}$
- Find $z=h(y)$
In previous example, $h: \mathbf{R} \rightarrow \mathbf{R}$
In general: $h:\mathbf{R}^{k} \rightarrow \mathbf{R}^{n-k}$
$w=z-h(y)$
$\dot{w}=\dot{z}-\frac{\partial h}{\partial y}\dot{y}=0$ for $w(0)=0$
$=A_2 z+g_2(y,z)-\frac{\partial h}{\partial y}(A_1y+g_1(y,z))=0$
$A_2h(y)+g_2(y,h(y))-\frac{\partial h}{\partial y}(A_1y+g_2(y,h(y)))=0$
- Find "reduced" system
$\dot{y}=A_1y+g_1(y,h(y))$
- Analysis stability of "reduced" system

$J=\begin{bmatrix} J_1 & 0 & ... & 0 \\ 0 & J_2 & ... & 0\\ 0& 0& ...&0\\ 0& 0& ... & J_r\end{bmatrix}$
where $r \leq n$
$J_i:$ submatrix of one of the following
$J_i=\begin{bmatrix} \lambda_i & 1 & ... &0 \\ 0& \lambda_i & ... & 0 \\ 0 & 0 & ... & 1 \\ 0 & 0 & 0 & \lambda_i\end{bmatrix}$ or $J_i=\begin{bmatrix} a_i & b_i \\ -b_i & a_i\end{bmatrix}, \lambda_i=a_i \pm jb_i$

---
$A=\begin{bmatrix}2 & 0 \\ 0 & 3\end{bmatrix}$
$J=\begin{bmatrix}2 & 0 \\ 0&3\end{bmatrix}$
$T=\begin{bmatrix} 1 & 0 \\ 0 & 1\end{bmatrix}$

---
$A=\begin{bmatrix} 1 & 0 \\ 0 & 1\end{bmatrix}$
$\lambda=1,1$
dimension of $\mathcal{N}(A-\lambda I)=$ geometric multiplicity of $\lambda$
$Av=\lambda v$
$v$ is an eigenvector corresponding to eigenvalue $\lambda$
$(A-\lambda I)v=0$
$v \in \mathcal{N}(A-\lambda I)$
$A-\lambda I=\begin{bmatrix} 1 & 0 \\ 0 & 1\end{bmatrix}-(1)\begin{bmatrix} 1 & 0 \\ 0 & 1\end{bmatrix}=\begin{bmatrix} 0 & 0 \\ 0 & 0\end{bmatrix}$
$\mathcal{N}(\begin{bmatrix} 0 & 0 \\ 0 & 0\end{bmatrix})=\mathbf{R}^2$

---
$A=\begin{bmatrix} 1 & 1 \\ 0 & 1\end{bmatrix}$
 $A-\lambda I=A=\begin{bmatrix} 1-\lambda & 1 \\ 0 & 1-\lambda\end{bmatrix}$
 $det(A-\lambda I)=(1-\lambda)^2=0$
 Algebraic multiplicity $=2$
 $\lambda=1,1$
 $A-\lambda I=\begin{bmatrix} 1 & 1 \\ 0 & 1\end{bmatrix}-(1)\begin{bmatrix} 1 & 0 \\ 0 & 1\end{bmatrix}=\begin{bmatrix} 0 & 1 \\ 0 & 0\end{bmatrix}$
$\mathcal{N}(\begin{bmatrix} 0 & 1 \\ 0 & 0\end{bmatrix})=\{\begin{bmatrix}1\\0\end{bmatrix}\}$
$dim \mathcal{N}(\begin{bmatrix} 0 & 1 \\ 0 & 0\end{bmatrix})=1=$geometric multiplicity of $\lambda=1$
$(A-\lambda I)^2 v=0$

---
Ex.
$\lambda=0,0$
geometric multiplicity $=1$
$J=\begin{bmatrix} 0 & 1 \\ 0 & 0 \end{bmatrix}$

$\lambda:$ algebraic multiplicity $4$, geometric multiplicity $2$
$J=\begin{bmatrix} \lambda & 1 & 0 & 0 \\ 0 & \lambda & 0 & 0 \\ 0 & 0 & \lambda & 1\\ 0 & 0 &0& \lambda\end{bmatrix}$ or $J=\begin{bmatrix} \lambda & 1 & 0 & 0 \\ 0 & \lambda & 1 & 0 \\ 0 & 0 & \lambda & 0\\ 0 & 0 &0& \lambda\end{bmatrix}$
where $J_1=\begin{bmatrix} \lambda & 1 \\ 0 & \lambda \end{bmatrix}, J_2=\begin{bmatrix} \lambda & 1 \\ 0 & \lambda \end{bmatrix}$ for first $J$
where $J_1=\begin{bmatrix} \lambda & 1 & 0 \\ 0 & \lambda & 1  \\ 0 & 0 & \lambda \end{bmatrix}, J_2=\lambda$ for second $J$

---
$\dot{x}=f(t,x), x(t_0)=x_0 ... (1)$
<u>Existence and Uniqueness</u>
Given $f(t,x), x_0, t_0,$ does $(1)$ have a solution $x(t)$ and if it is unique?

DT:
$x_{t+1}=f(x_t), x(t_0)=x_0$
fixed point: $x=f(x)$

---
<u>Fixed point Theorems</u>
Contraction Mapping Theorem
If $(0)$
![[Pasted image 20260212182440.png]]
$(1) U:$ closed subset of a Banach Space 
and $(2): |T(x)-T(y)| \leq \rho |x-y|$ for $\rho <1, \forall x,y \in U$
then $T$ has a unique fixed point in $U$
and the solutions of $x_{n+1}=T(x_n)$ converge to this fixed point from any $x_0 \in U$

Recall $x_{t+1}=r x_t (1-x_t)$
![[Pasted image 20260213114520.png]]
$T=rx(1-x)$
$r=1: U=[0,1], T=x(1-x)$
$r=4:$
![[Pasted image 20260213114602.png]]
$T(x)-T(y)=r|x(1-x)-y(1-y)|$
$=r|(x-y)-(x^2-y^2)|$
$=r|(x-y)-(x-y)(x+y)|$
$=r|(x-y)(1-(x+y))|$
$=r|x-y| |1-(x+y)|$
$<r|x-y|(1+x+y)$
$<3r|x-y|$
where $3r = \rho<1$
$r < \frac{1}{3}$ contraction

---

Alternatively,
$|T(x)-T(y)|<r |x-y| |1-2|$
or $|T(x)-T(y)|<r |x-y| |1-0|$
$|T(x)-T(y)|<r |x-y|$
$r<1 \implies \rho<1$

Normed vector (linear) space
$X:$ vector space
$|\cdot|:$ norm
- $|x|\geq 0, \forall x \in X$
- $|x+y| \leq |x|+|y|, \forall x, y \in X$
- $|\alpha x|=|\alpha| \cdot |x|, \forall \alpha \in \mathbf{R}, x \in X$

Ex.
$C^n[a,b]:$ the set of all continuous functions $[a,b] \rightarrow \mathbf{R}^n$ with norm $|x|_c=\max_{t \in [a,b]}|x(t)|$
Alternative: $|x|_c := \int_{a}^{b} |x(t)|^2dt$

## Class 9
Definition: A normed vector space $X$ is Banach if every Cauchy sequence converges to an element in $X$

---
Ex.
A converging sequence where the "limit" does not belong to the set
$a_n=\frac{1}{n}, n=1,2,...$
$a_n \in (0,1] \forall n$
But $\lim_{n \rightarrow \infty} a_n=0 \neq (0,1]$

---
<u>Cauchy Sequence</u>
A sequence $\{a_n\}$ is set to be Cauchy if $|a_n-a_m| \rightarrow 0$ as $n,m\rightarrow \infty$
Every convergent sequence is Cauchy
but not every Cauchy sequence is convergent

---
A sequence $\{a_n\}$ is called convergent to $a^{\ast}$
if for every $\epsilon>0$, there exist $\mathcal{N}(\epsilon)$ such that
$|a_n-a^{\ast}|<\epsilon ,\forall n > \mathcal{N}(\epsilon)$

---
![[Pasted image 20260213121255.png]]
Claim: $C^n[a,b]$ is Banach

---
Back to CT system (existence and uniqueness)
$\dot{x}=f(t,x), x(0)=x_0   ...(\star)$
we want to show existence and uniqueness of $x(t) \in [0,\delta]$ that satisfies $(\star)$
$x(t)=x(0)+\int_{0}^{t}f(\tau, x(\tau))d\tau= T(x)(t)$

DT systems
$x[k+1]=f[k,x[k]]$
$=f[k,f[k-1,x[k-1]]]$
$...$
$=f[k,f[k-1,...f[0,...]]]$

![[Pasted image 20260213144734.png]]
$\tilde{x}(s) :=x_0+\int_{0}^{s}f(\tau, x(\tau))d\tau$
$\tilde{x}(s)=T(x)(s)$
$x(t)=x(0)+\int_{0}^{t}f(\tau, x(\tau))d\tau= T(x)(t)$
$\implies x=T(x)$
Let's investigate application of contraction mapping to $T(x)$
$(0):$ ![[Pasted image 20260213144856.png]]
$(1): U(\delta) \subseteq C^n[0,\delta]:$ Banach space
$(2):$ contraction
$\implies \exists$ a unique $x^{\ast} \in U(\delta)$ such that $x^{\ast}=T(x^{\ast})$ and $...$
$U(\delta, r) =\{x \in C^n[0,\delta]: \max_{t\in [0,\delta]} |x(t)-x_0|<r\}$
closed $\implies (1)$ is satisfied

---
$C^n[0,\delta]$
![[Pasted image 20260213145142.png]]

---
![[Pasted image 20260213145153.png]]
A sufficient condition is $f(t,x)$ is continuous in $t,x$

Ex. $f(t,x)=x+u(t)$
$u(t)$ could be discontinuous on $x$

---
Need to show this: $\max_{t\in [0,\delta]} |x(t)-x_0|<r$
$T(x)(t)-x_0=\int_{0}^{t}f(\tau, x(t))dt$
where $T(x)(t)=x_0+\int_{0}^{t} f(\tau, x(\tau))d\tau$
$\int_{0}^{t}f(\tau, x(\tau))d\tau-\int_{0}^{t} f(\tau, x_0)d\tau+\int_{0}^{t}f(\tau, x_0)d\tau$
$|T(x)(t)-x_0|<\int_{0}^{t} |f(\tau, x(\tau)-f(\tau, x_0))|d\tau+\int_{0}^{t}|f(\tau, x_0)|d\tau$

---
Suppose $f(t,x)$ is Lipschitz in $x$, uniformly in $t \in [0,\delta]$
$\implies |f(t,x)-f(t,y)|$ $x,y \in B_r(x_0)$
$<L|x-y|, \forall t \in [0,\delta]$
$f(t,x_0)$ is bounded say by $h$, because $f(t,x_0)$ is continuous over $[0,\delta]$
$|T(x)(t)-x_0|< \int_{0}^{t} L|x(\tau)-x_0|d\tau+\int_{0}^{t}hdt$
$< \int_{0}^{t}Lrd\tau+\int_{0}^{t}hd\tau$
$=Lrt+ht$
$<(Lr+h) \delta$
$<r$ (want)
Need $\frac{(Lr+h)\delta}{r} \leq 1 \implies \delta \leq \frac{r}{Lr+h}$
$\rightarrow (2) |T(x)-T(y)|<\rho |x-y|, \rho<1$
$\forall x,y \in U(\delta, r)$
$x \in U(\delta, r) \rightarrow |x-x_0|<r$
$|x-y|=|x-x_0+x_0-y|$
$<|x-x_0|+|y-x_0|$
$<2r$
$...$

Ex.
$\dot{x}=x^{\frac{1}{3}}=f(x)$
$\frac{\partial f}{\partial x} =\frac{1}{3} x^{-\frac{1}{3}}|_{x=0}=\infty$
Not Lipschitz
![[Pasted image 20260213150232.png]]


## Class 10
$(2)|T(x)-T(y)| < \rho |x-y|, \rho <1$
$\forall x,y \in U(\delta, r)$
$|T(x)-T(y)|=\max_{t \in [0,\delta]} |T(x)(t)-T(y)(t)|$
$|T(x)(t)-T(y)(t)|=|\int_{0}^{t}f(\tau, x(\tau))d\tau-\int_{0}^{t}f(\tau, y(\tau))d\tau|$
$\leq \int_{0}^{t}|f(\tau,x(\tau))-f(\tau,y(\tau))|d\tau$
$\leq \int_{0}^{t} L|x(\tau)-y(\tau)|d\tau$
Recall $x,y \in U(\delta)$
$|x(\tau)-x_0| \leq r ,\forall \tau$
$|y(\tau)-x_0|\leq r, \forall r$
$|x(\tau)-y(\tau)|\leq 2r , \forall r$
$|T(x)(t)-T(y)(t)|=\leq \int_{0}^{t} L|x(\tau)-y(\tau)|d\tau$
$|x(\tau)-y(\tau)|\leq |x-y|$
$|T(x)(t)-T(y)(t)|\leq  L|x-y|t$
$\leq L\delta |x-y|$
where $L \delta= \rho$
we need $\rho<1 \implies \delta L <1$
$\delta < \frac{1}{L}$
Last time $\delta \leq \frac{r}{Lr+h}$
$\frac{r}{Lr+h} \leq \frac{1}{L}$
$Lr \leq Lr+h$
Therefore, $\delta \leq \frac{r}{Lr+h}$ ensure invariance and contraction
Contraction Mapping Theorem:
$\implies \exists$ unique $x \in U(\delta)$ which is a fixed point of $x=T(x)$
"globally  attractive" from any $x^{(0)} \in U(\delta)$
$x^{(1)}=T(x^{(0)})$
If $f(t,x)$ is continuous in $t$ and Lipschitz in $x$
$\implies \dot{x}=f(t,x), x(0)=x_0$ has unique solution in $[0,\delta]$ for $\delta \leq \frac{r}{Lr+h}$
![[Pasted image 20260213151822.png]]
Because $\delta$ depends on $L(x(0))$, we cannot readily claim existence and uniqueness over $[0,\infty]$
Recall:
$\dot{x}=x^2$
$f(x)=x^2$
$|f(x)-f(y)|=|x^2-y^2|=|x-y||x+y|$

---
If in addition, $f(t,x)$ is globally Lipschitz in $x$, then $\exists$ unique solution for all $t$

$\dot{x}=-x^3$
$\frac{dx}{dt}=-x^3$
$-\frac{dx}{x^3}=dt$
$\frac{x^{-2}}{2}|_{x_0}^{x}=t$
$x^{-2}-x_0^{-2}=2t$
$x^{-2}=2t+x_0^{-2}$
$x^2=\frac{1}{2t+x_0^{-2}}$
$x=sgn(x) \sqrt{\frac{1}{2t+\frac{1}{x_0^2}}}$
$f(x)=x^3$ is not globally Lipschitz and yet a unique solution for all $t$

---
Ex.
$\dot{x}=x^{\frac{1}{3}}=f(x), x(0)=0$
$\frac{\partial f}{\partial x} =\frac{1}{3} x^{-\frac{1}{3}}|_{x=0}=\infty$
Not Lipschitz
![[Pasted image 20260213150232.png]]
$x(t)=0$
$x(t)=(\frac{2t}{3})^{\frac{3}{2}}$
$\dot{x}=\frac{3}{2} (\frac{2t}{3})^{\frac{1}{2}} \frac{2}{3}$
$=(\frac{2t}{3})^{\frac{1}{2}}$
$=[(\frac{2t}{3})^{\frac{3}{2}}]^{\frac{1}{3}}$
$=x^{\frac{1}{3}}$

$C^0:$ continuing
Lipschitz
$C^1:$ continuous differtiable
![[Pasted image 20260213152522.png]]
![[Pasted image 20260213152528.png]]

---
$\dot{x}=f(t,x; \mu), x(0)x_0$

Continuous dependence on initial condition:
$\dot{x}=f(t,x)$
$x_0, y_0:$ two initial conditions
$x(t), y(t)$
continuous dependence on $[0,\tau]$
For any $\epsilon>0, \exists \delta(\epsilon, \tau)>0$
s.t. $|x_0-y_0| \leq \delta \implies |x(t)-y(t)| \leq \epsilon, \forall t [0,\tau]$
if $x(t),y(t)$ remain in a set with Lipschitz constant $L$ over $[0,\tau]$
![[Pasted image 20260213152809.png]]

---
$\dot{x}=f(t,x; \mu)$
$\dot{\mu}=0$
$X=\begin{bmatrix} x \\ \mu \end{bmatrix}$
$X_0=\begin{bmatrix} x_0 \\ \mu \end{bmatrix}$
$\dot{X}=F(t,X)$
$F=\begin{bmatrix} f(t,X) \\ 0\end{bmatrix}$

<u>Sensitivity to parameters</u>
$\dot{x}=f(t,x,\mu), x(0)=x_0$
$\mu=\mu_0$ (nominal)
$\phi(t,x_0;\mu):x(t)$ starting from initial condition $x_0$ with model parameter $\mu$
where $\phi(t,x_0;\mu)=x_0+\int_{0}^{t}f(t,x(\tau);\mu)d\tau$
sensitivity matrix: $(n\times p)$
$S()t,x_0,\mu:=\frac{\partial \phi(t,x_0,\mu)}{\partial \mu}$
$x \in \mathbf{R}^{n} \rightarrow \phi \in \mathbf{R}^{n}, \mu \in \mathbf{R}^{p}$
$S=\begin{bmatrix} \frac{\partial \phi_1}{\partial \mu_1} & ... & \frac{\partial \phi_1}{\partial \mu_p}\\ ... & ...&...\\ \frac{\partial \phi_n}{\partial \mu_1} &...& \frac{\partial \phi_n}{\partial \mu_p}\end{bmatrix}$
$\phi(t,x_0,\mu)=\begin{bmatrix} \phi_1(t,x_0,\mu) \\ ... \\ \phi_n(t,x_0,\mu)\end{bmatrix}$

---
$\phi(t,x_0,\mu)=x_0+\int_{0}^{t}f(t,x(\tau);\mu)d\tau$
$\frac{\partial \phi}{dt}=f(t,x(t),\mu)$
$\frac{\partial S}{dt}=\frac{\partial }{dt} \frac{\partial \phi}{\partial \mu}$
$=\frac{d }{d \mu} \frac{\partial \phi}{dt}$
$=\frac{d }{d \mu}f(t,x(t),\mu)$
$=\frac{d}{d\mu} f(t, \phi(t,x_0,\mu),\mu)$
$=\frac{\partial}{\partial \mu} f(t,\phi(t,\mu),\mu)+\frac{\partial f(t,\phi,\mu)}{\partial \phi}  \frac{\partial \phi}{\partial \mu}$
$S(0,x_0,\mu):$ initial condition

## Class 11
$\phi(t,x_0,\mu)=x_0+\int_{0}^{t}f(t,x(\tau);\mu)d\tau$
$\frac{\partial \phi}{dt}=f(t,x(t),\mu)$
$\frac{\partial S}{dt}=\frac{\partial }{dt} \frac{\partial \phi}{\partial \mu}$
$=\frac{d }{d \mu} \frac{\partial \phi}{dt}$
$=\frac{d }{d \mu}f(t,x(t),\mu)$
$=\frac{d}{d\mu} f(t, \phi(t,x_0,\mu),\mu)$
$=\frac{\partial}{\partial \mu} f(t,\phi(t,\mu),\mu)+\frac{\partial f(t,\phi,\mu)}{\partial \phi}  \frac{\partial \phi}{\partial \mu}$
$S(0,x_0,\mu):$ initial condition$=0$

---
$[\frac{\partial S}{\partial t}]_{n \times p}=A(t,\mu) |_{\mu=\mu_0} [s]_{n \times p}+B(t,\mu) |_{\mu=\mu_0}$
$[A(t,\mu)]_{n \times n} =\frac{\partial f}{\partial \phi} (t,\phi(t,\mu),\mu)$
$[B(t,\mu)]_{n \times p}=\frac{\partial f}{\partial \mu}(t,\phi(t,\mu),\mu)$

Ex.
$\dot{x}_1=-\mu x_2$
$\dot{x}_2=\mu x_1$
$n=2,p=1$
$f(x,\mu)=\begin{bmatrix} -\mu x_2 \\ \mu x_1\end{bmatrix}$
$A(t,\mu)=\frac{\partial f}{\partial x}=\begin{bmatrix} 0 & -\mu \\ \mu & 0 \end{bmatrix}$
$B(t,\mu)=\frac{\partial f}{\partial \mu}=\begin{bmatrix}-x_2 \\ x_1\end{bmatrix}$
$\frac{\partial S}{\partial t}=\frac{\partial f}{\partial x}=\begin{bmatrix} 0 & -\mu \\ \mu & 0 \end{bmatrix} S+\begin{bmatrix}-x_2 \\ x_1\end{bmatrix}$
$S=\begin{bmatrix} S_1 \\ S_2\end{bmatrix}$
$\begin{bmatrix} \dot{S}_1 \\ \dot{S}_2\end{bmatrix}=\begin{bmatrix} 0 & -\mu \\ \mu & 0 \end{bmatrix} \begin{bmatrix} S_1 \\ S_2\end{bmatrix}+\begin{bmatrix}-x_2 \\ x_1\end{bmatrix}$
$x(t,\mu_0)$
$x(t,\mu) \approx x(t,\mu_0)+[S(t)]_{n \times p} (\mu-\mu_0)_{p \times 1}$

---
Ex.
$\dot{x}_1=x_2$
$\dot{x}_2=-c \sin{x_1}-(a+b \cos{x_1})x_2$
$a_0=1, b_0=0, c_0=1$
$n=2,p=3$
$S: \begin{bmatrix} x_3 & x_5 & x_7\\ x_4 & x_6 & x_8\end{bmatrix}$
$\dot{S}=A(t,\mu)|_{\mu=\mu_0}+B(t,\mu)$
$A(t,\mu)=\frac{\partial f}{\partial x}=\begin{bmatrix} 0 & 1 \\ -c \cos{x_1}+bx_2 \sin{x_1} & -(a+b \cos{x_1})\end{bmatrix}$
$B(t,\mu)=\frac{\partial f}{\partial \mu}=\begin{bmatrix} 0 & 0 & 0\\ -x_2 & -x_2 \cos{x_1} & -\sin{x_1}\end{bmatrix}$
$A(t,\mu)|_{\mu=\mu_0}=\begin{bmatrix} 0 & 1 \\ -\cos{x_1}&-1\end{bmatrix}$
$B(t,\mu)|_{\mu=\mu_0}=\begin{bmatrix} 0 & 0 & 0 \\ -x_2 & -x_2 \cos{x_1} & -\sin{x_1}\end{bmatrix}$
$\begin{bmatrix} \dot{x}_2 & \dot{x}_5 & \dot{x}_7 \\ \dot{x}_4 & \dot{x}_6 & \dot{x}_8\end{bmatrix}=\begin{bmatrix} 0 & 1 \\ -\cos{x_1}&-1\end{bmatrix} \begin{bmatrix} x_3 & x_5 & x_7\\ x_4 & x_6 & x_8\end{bmatrix}+\begin{bmatrix} 0 & 0 & 0 \\ -x_2 & -x_2 \cos{x_1} & -\sin{x_1}\end{bmatrix}$
$\mu=\begin{bmatrix} a \\ b \\c \end{bmatrix}$
$\mu_0=\begin{bmatrix} a_0 \\ b_0 \\ c_0\end{bmatrix}$
$\begin{bmatrix} \dot{x}_1 \\ \dot{x}_2 \\ \dot{x}_3 \\ \dot{x}_4 \\ \dot{x}_5 \\ \dot{x}_6 \\ \dot{x}_7 \\ \dot{x}_8\end{bmatrix}=\begin{bmatrix} x_2 \\ -\sin{x_1}-x_2\\ x_4\\ -x_3 \cos{x_1}-x_4-x_2\\ x_6\\ -x_5 \cos{x_1}-x_6-x_2 \cos{x_1}\\ x_8 \\ -x_7 \cos{x_1}-x_8-\sin{x_1}\end{bmatrix}$
$\begin{bmatrix} x_1(t,\mu) \\ x_2(t,\mu)\end{bmatrix} \approx \begin{bmatrix} x_1(t,\mu_0) \\ x_2(t,\mu_0)\end{bmatrix}+\begin{bmatrix} x_3(t,\mu_0) & x_5 & x_7\\ x_4(t,\mu_0) & x_6 & x_8\end{bmatrix}\begin{bmatrix} a-a_0 \\ b-b_0 \\ c-c_0\end{bmatrix}$
![[Pasted image 20260225192925.png]]
$\mu$ is scalar
$\mu \in [\mu_0 - \delta , \mu_0+\delta]$

---
<u>Lyapunov Stability Theorem</u>
$\dot{x}=f(x)$
WLOG, $x(0)=0$
if $eq^{m}$ is at $x^{\ast} \neq 0$
$\tilde{x}=x-x^{\ast}$
$x=\tilde{x}+x^{\ast}$
$\dot{\tilde{x}}=\dot{x}-\dot{x^{\ast}}=\dot{x}=f(x)=f(\tilde{x}+x^{\ast})$
$\dot{\tilde{x}}=f(\tilde{x}+x^{\ast})$

---
$\dot{x}=-x+1=f(x)$
$x^{\ast}=1$
$\dot{\tilde{x}}=f(\tilde{x}+x^{\ast})$
$=f(\tilde{x}+1)$
$=-(\tilde{x}+1)+1$
$\dot{\tilde{x}}=-\tilde{x}$ vs. $\dot{\tilde{x}}=-\tilde{x}+1$

<u>Lyapunov Stability</u>
$x=0$ is stable (in Lyapunov sense) if given $\epsilon>0, \exists \delta(\epsilon)>0$ s.t.
$|x_0| \leq \delta \implies |x(t)| \leq \epsilon ,\forall t \geq 0$
![[Pasted image 20260225194347.png]]
![[Pasted image 20260225194354.png]]
If not stable $\implies$ unstable
i.e., if $\exists \tilde{\epsilon}>0, T(\epsilon)>0$ s.t. $\forall \delta>0$
$|x(t)|> \epsilon ,\forall t \geq T$
![[Pasted image 20260225194543.png]]
$x=0$ is Asymptotically stable (Local) if it is stable $x(t) \rightarrow 0$ in a neighborhood of $x=0$
![[Pasted image 20260225194628.png]]
$x=0$ is globally Asymptotically stable (GAS) if stable and $x(t) \rightarrow 0, \forall x(0)$
![[Pasted image 20260225194707.png]]

<u>Lyapunov's Stability Theorem</u>
$\dot{x}=f(x), x \in \mathbf{R}^n$
1. Let $D$ be an open, connected subset of $\mathbf{R}^n$ that includes $x=0$
If there exists a $\mathbf{C}^1$ function
$V:D \rightarrow \mathbf{R}$ such that
$V(0)=0$ and $V(x)>0, \forall x \in D|\{0\}$
and $\dot{V}(x) := \frac{d}{dt}V(X)=\nabla V^T(x) \frac{dx}{dt}=\nabla V^T(x) f(x)$
then $x=0$ is stable
2. If $\dot{V}(x)<0, \forall x \in D|\{0\}$
then $x=0$ is asymptotically stable

## Class 12
$\nabla^T (x) \cdot f(x)\leq 0$
$\Omega_c:=\{x:V(x) \leq c\}, c>0$
where $\Omega_c$ is the level set of the Lyapunov set, 

Ex.
$V(x)=x^2$
![[Pasted image 20260225202223.png]]
$V(x)=x^2$
![[Pasted image 20260225202245.png]]
$V(x)=1-e^{-x^2}$
![[Pasted image 20260225202313.png]]
$\Omega_c =\mathbf{R}, c>1$

Recall:
$V(x)$ is continuous at $x=0$
$\forall \epsilon>0, \exists \delta(\epsilon)>0$ s.t.
$|x-0| \leq \delta \implies |V(x)-V(0)| \leq \epsilon$
i.e., $x \in \mathbf{B}_\delta \implies V(x)\leq \epsilon$

---
$\Omega_c$ is bounded for sufficiently small $c>0$
![[Pasted image 20260225202641.png]]
$\epsilon_2 := inf_{x \in \Omega_\epsilon | B_{\delta 1}} V(x)>0$
Claim $\epsilon_{\epsilon_2/2}$ is bounded

To prove: $x=0$ is stable
given any $\epsilon>0, \exists \delta(\epsilon)>0$
s.t. $|x_0|\leq \delta \implies |x(t)| \leq \epsilon , \forall t \geq 0$
![[Pasted image 20260225202915.png]]

2. 
Suppose there is an initial condition $x_0$
s.t. starting from that I.C. $x(t) \nrightarrow 0$
$\implies V(x) \nrightarrow 0$
But $V(x(t)) \rightarrow 0, c>0$
$\dot{V}<0$ and $V \geq 0$
![[Pasted image 20260225203432.png]]
$\gamma =\max_{x: c \leq V(x) \leq V(x_0)} -\dot{V}(X)$
$\implies \dot{V}(x) \leq -\gamma, \forall t \geq 0$
$V(x)=V(x_0) +\int_{0}^{t} \dot{V}(x(\tau))d\tau$
$\leq V(x_0)-\gamma t$
$<0$ for sufficiently high $t$
a contradiction to $V(x) \geq 0$
Therefore $x(t)$ will goes to 0

Ex.
$f(x)=1+e^{-x}$
![[Pasted image 20260225203639.png]]
$\frac{df}{dx}=-e^{-x} <0$

---
3. If, in addition, $D=\mathbf{R}^n$ and $|x| \rightarrow \infty \implies V(x) \rightarrow \infty$ (radially unbounded)
then $x=0$ is GAS

Ex.
$V(x)=\frac{x_1^2}{1+x_1^2}+x_2^2$
Not radially unbounded

Ex.
$\dot{x}=-g(x), x \in \mathbf{R}$
$V(x)=\frac{1}{2} x^2$
$\dot{V}(x)=\frac{\partial V}{\partial x}\dot{x}$
$=2x(-g(x))$
$xg(x) >0$
$<0$ if $x\neq 0$
$x=0$ is GAS
![[Pasted image 20260225203939.png]]

Ex.
$\ddot{x}=-a\dot{x}-g(x)$
$x_1=x$
$x_2=\dot{x}_1$
$\dot{x}_2=\ddot{x}=-ax_2-g(x_1)$
$\dot{x}_1=x_2$
$V(x)=\frac{1}{2} x_1^2 +\frac{1}{2}x_2^2$
$\dot{V}(x)=\nabla^TV(x)f(x)$
$\begin{bmatrix} x_1 & x_2\end{bmatrix} \begin{bmatrix} x_2 \\ -ax_2-g(x_1)\end{bmatrix}$
$\nabla V(x)=\begin{bmatrix}x_1 \\ x_2\end{bmatrix}$
$\dot{V}(x)=x_1x_2+x_2(-ax_2-g(x_1))$
$=x_1x_2-ax_2^2-x_2g(x_1)$
$V(x)=\int_{0}^{x_1}g(y)dy+\frac{1}{2}x_2^2$
$\frac{\partial V}{\partial x_1}=g(x_1)$
$\frac{\partial V}{\partial x_2}=x_2$
$\dot{V}=g(x_1)x_2+x_2(-ax_2-g(x_1))$
$=g(x_1)x_2-ax_2^2-x_2g(x_1)$
$\dot{V}=-ax_2^2$
$a<0:$ no conclusion
$a=0:$stable
$a>0:$stable

$x=0$ is stable
LaSalle:
$x=0$ is GAS
$\Omega_c \leftarrow$ disks
$S:x_1$ axis
![[Pasted image 20260225205135.png]]

<u>LaSalle-Krasinski Invariance Principle</u> 
Time invariant system
Allow to conclude AS from $\dot{V}(x) \leq 0$ if additional conditions hold

## Class 13
Suppose
$\Omega_c =\{x:V(x) \leq c\}$ is bounded and $\dot{V}(x) \leq 0$ in $\Omega_c$
Using Lyapunov stability theory, we could already conclude that:
if $x(0) \in \Omega_c$
then $x(t) \in \Omega_c, V(t)\rightarrow \tilde{c} \subset c$
and therefore $x(t) \rightarrow \Omega_{\tilde{c}}$
$S:=\{x \in \Omega_c: \dot{V}(x)=0\}$
$M$ is the largest invariant set in $S$
$x(t) \rightarrow M, \forall x(0)\in \Omega_c$
![[Pasted image 20260225210156.png]]

Ex.
$\dot{y}=ay+u$
$u=-ky$
$\dot{k}=\gamma y^2, \gamma>0$
$\dot{y}=ay-ky$
$\dot{k}=\gamma y^2$
$x_1=y, x_2=k$
$\dot{x}_1=f_1(x_1,x_2)=ax_1-x_1x_2$
$\dot{x}_2=f_2(x_1,x_2)=\gamma x_1^2$
Consider the following Lyapunov function candidate
$V(x)=\frac{1}{2}x_1^2+\frac{1}{2\gamma}(x_2-b)^2, b>a$
$\dot{V}(x)=x_1\dot{x}_1+\frac{1}{\gamma}(x_2-b)\dot{x_2}$
$=x_1(ax_1-x_1x_2)+\frac{1}{\gamma}(x_2-b)(\gamma x_1^2)$
$=ax_1^2-bx_1^2$
$=(a-b)x_1^2 \leq 0 (b>a)$
$(0,b)$ is stable

LaSalle
![[Pasted image 20260225210514.png]]
$\dot{V}=0$
$M=S$
$x(t) \rightarrow M$ ($x_2-$axis)
$x_1(t) \rightarrow 0$

Back to linear system $\dot{x}=Ax$
Recall
$x=0$ is table if $Re\{\lambda_i(A)\}\leq 0, \forall i$
and the e-values on the imaginary axis have Jordan blocks of order one
If $Re\{\lambda_i(A)\}$ (Hurwitz) $<0 \implies$ AS
$V(x)=X^TPX, P=P^T>0$
$\dot{V}(x)=X^TP\dot{X}+\dot{X}^TPX$
$=X^TPAX+X^TA^TPX$
$=X^T(PA+A^TP)X$
$=-X^TQX$
$(PA+A^TP)^T=A^TP^T+P^TA$
$=A^TP+PA$
$A^TP+PA=-Q$

---
$P=\int_{0}^{\infty} e^{A^Tt}Qe^{At}dt$
- $P>0$
$X^TPX=\int_{0}^{\infty} X^T e^{A^Tt}Q e^{At}Xdt$
where $y:=e^{At}X, y^T=X^Te^{A^Tt}$
- $A^TP+PA=-Q$
$=\int_{0}^{\infty} (A^Te^{A^Tt}Qe^{At}+e^{A^Tt}Qe^{At}A)dt$
where $A^Te^{A^Tt}Qe^{At}+e^{A^Tt}Qe^{At}A=\frac{d}{dt}(e^{A^Tt} Q e^{At})$
$\frac{d}{dt}(e^{At})=\frac{d}{dt}(I+At+\frac{A^2 t^2}{2!}+...)$
$=A+A^2 t+\frac{A^3t^2}{2!}+...$
$=A(I+At+\frac{A^2t^2}{2!}+...)$
$=Ae^{At}$
$=e^{At}A$
$\frac{d}{dt}(e^{A^Tt}Qe^{At})=e^{A^Tt}Q \frac{d}{dt}(e^{At})+\frac{d}{dt}(e^{A^Tt})Qe^{At}$
$=e^{A^Tt}Qe^{At}A+A^Te^{A^Tt}Qe^{At}$ - QED
Therefore $A^TP+PA=e^{A^Tt}Q e^{At}|_{0}^{\infty}$
$=0-Q$
$=-Q$

## Class 14

$V(x)=x^T P x$
$P=I: V(x)=x^T x$
$\dot{V}(x)=\dot{x}^T x+ x^T \dot{x}$
$=x^T(A^T+A)x$
may be sign-definite even if $A$ is Hurwitz
(See example on the next page)
Ex.
$A=\begin{bmatrix} -1 & 4 \\ 0 & -1\end{bmatrix}$
$\lambda=-1,-1$ Hurwitz
$A^T=\begin{bmatrix} -1 & 0 \\ 4 & -1\end{bmatrix}$
$A+A^T=\begin{bmatrix} -2 & 4 \\ 4 & -2\end{bmatrix}=2\begin{bmatrix} -1 & 2\\ 2 &-1\end{bmatrix}$
Trace$<0 \leftrightarrow \sum_{i} \lambda_i<0$
Det $<0 \leftrightarrow \prod_{i} \lambda_i <0$
$\implies$ one $\lambda$ is positive
$A+A^T$ is not Hurwitz

- $Q=I \rightarrow P \rightarrow$ estimate $R$
![[Pasted image 20260307142143.png]]

<u>Region of Attraction</u>
$\dot{x}=f(x)$
$x=0$ is the equilibrium point
$R=\{x| \phi(t,x)=0\}$
$\phi(t,x) \equiv x(t)$ starting from $x$ at $t=0$
![[Pasted image 20260307142946.png]]
$R$ is invariant
$\phi(t,x) \rightarrow 0$
$x \in \mathbf{R} \implies x(s) \in \mathbf{R} ,\forall s$
$\implies \phi(t,x(s)) \rightarrow^? 0$
$\implies \phi(t,\phi(s,x))\rightarrow^? 0$
$\implies \phi(t+s, x) \rightarrow^? 0$

Ex.
$\dot{x}_1=-ax_1+x_2$
$\dot{x}_2=\frac{x_1^2}{1+x_1^2}-bx_2$
$x_2=ax_1$
$\frac{x_1^2}{1+x_1^2}=abx_1$
$\implies x_1=ab(1+x_1^2)$
![[Pasted image 20260307144857.png]]
$R$ is an open, connected, invariant set
Boundaries of $R$ are trajectories
In practice, use $V(x)$ (Lyapunov function) for under-approximation of $R$:
$\implies$ find largest $c$ such that $\Omega_c \subset R$ $(\dot{V}(x)<0)$

Ex.
$\dot{x}=\begin{bmatrix}-2 & 0 \\ 0 & 0 \end{bmatrix}$
$\dot{x}_1=-2x_1$
$\dot{x}_2=0$
![[Pasted image 20260307145059.png]]
When $A$ is diagonalizable
$x(t)=e^{\lambda_1 t} < w_1^{\ast}, x(0)> v_1+...+e^{\lambda_n t} <w_n^{\ast},x(0)>v_n$

<u>Lyapunov Linearization Method</u>
$\dot{x}=f(x)=Ax+(f(x)-Ax)$
where $f(x)-Ax=g(x)$
$A=\frac{\partial f}{\partial x}|_{x=0}$
$\dot{x}=Ax$
$g(0)=0$
$\exists \gamma>0, r>0$ ($|x|<r$)such that $|g(x)|<\gamma |x|$
$V(x)=x^T Px$
$A^TP+PA=-Q$
$\dot{V}(x)=\dot{x}^T Px+x^TP \dot{x}$
$=x^TP(Ax+g(x))+(Ax+g(x))^T Px$
$=x^T (PA+A^TP)x+2x^TPg(x)$
$=-x^TQx+2x^TPg(x)$
$\leq -x^TQx+2|x| ||P|| |g(x)|$
from $|Ax|\leq ||A|| |x|$
$\lambda_{min}(Q) |x|^2 \leq x^T Qx\leq \lambda_{max}(Q) |x|^2$
$\dot{V}(x) \leq -\lambda_{min}(Q)|x|^2+2|x| ||P|| |g(x)|$
$\leq \lambda_{min}(Q) |x|^2+2\gamma |x|^2 ||P||$
$\gamma< \frac{\lambda_{min}(Q)}{2 ||P||}$
$\implies \dot{V}(x) <0$
![[Pasted image 20260307145728.png]]

Ex.
$\dot{x}=-\frac{x}{1+t}$
$x(t)=x(t_0)\frac{1+t_0}{1+t}$
$t_0>-1$
$\dot{x}(t)=A(t)x$
$\dot{x}=f(x,t)$


## Class15
Definition: $x=0$ is stable if for every $\epsilon >0$ and $t_0$ there exists $\delta>0$ such that
$|x(t_0)| \leq \delta (t_0,\epsilon) \implies |x(t)| < \epsilon, \forall t \geq t_0$
If the same $\delta$ works for all $t_0$
i.e., $\delta=\delta(\epsilon)$ the $x=0$ is uniformly stable
$\epsilon=1$
$t_0:0 \rightarrow |x(t_0)| \leq 1 \leftarrow \delta$
$t_0:5 \rightarrow |x(t_0)|\leq 5 \leftarrow \delta$
$t_0:10 \rightarrow |x(t_0)|\leq 2 \leftarrow \delta$
$\implies \delta =1$

---
$\dot{x}=A(t)x$
$A(t)=\begin{bmatrix} -1+1\cdot 5 \cos^2 t & -1-1\cdot 5 \sin t  \cos t\\ -1-1\cdot 5 \sin t \cos t & -1+1\cdot 5 \sin^2 t\end{bmatrix}$
e-values: $-0.25 \mp j0.25 \sqrt{7}$
$x(t)=\begin{bmatrix} e^{0.5t} \cos t & e^{-t} \sin t\\ e^{-0.5t} \sin t & e^{-t} \cos t\end{bmatrix} x(0)$
where $\begin{bmatrix} e^{0.5t} \cos t & e^{-t} \sin t\\ e^{-0.5t} \sin t & e^{-t} \cos t\end{bmatrix}=\Phi(t,0)$

---
If $w_1(x) \leq V(t,x) \leq w_2(x)$ and $\dot{V}(t,x) \triangleq \frac{\partial V}{\partial t}+\frac{\partial V}{\partial x}f(t,x) \leq 0$
for some positive definite $w_1$ and $w_2$
then $x=0$ is uniformly stable

---
<u>Stability definition through comparison functions</u>
$k_{\infty} \subset k \subset$ Positive Definite
![[Pasted image 20260307152507.png]]
$x=0$ is uniformly stable if: $|x(t)| \leq \alpha (|x(t_0)|)$ for $|x(t_0)| <c$ for some $c>0$
$x=0$ is uniformly asymptotically stable
if there exists a class-KL function $\beta(\cdot, \cdot)$
such that $|x(t)|\leq \beta(|x(t_0)|, t-t_0)$
for $|x(t_0)|<c$ for some $c>0$
$\beta(\cdot, \cdot)$ is class-KL if:
1. $\beta(\cdot,s)$ is class $k$ for every fixed $s$
2. $\beta(r,\cdot)$ is decreasing and $\beta(r,s) \rightarrow 0$ as $s \rightarrow \infty$ for every fixed $r$

---
- If $w_1(x) \leq V(t,x) \leq w_2(x)$
and $\dot{V}(t,x) \leq -w_3(x)$ for some positive definite $w_3(\cdot)$
then $x=0$ is uniformly asymptotically stable
- $[+] w_1(x)$ is radially unbounded
$\implies x=0$ is uniformly GAS

Ex.
$\dot{x}=-x^3$ (Recall)
$V(x)=\frac{1}{2}x^2$
$\dot{V}(x)=x(-x^3)=-x^4 <0$ ($x\neq 0$)
radially unbounded
$\implies x=0$ is GAS

---
<u>Comparison Lemma</u>
$x \in \mathbf{R}$
$\dot{x}=f(x,t) \leq g(x), \forall t;x$
$\dot{x}=f(x,t)$
$\dot{\tilde{x}} = g(\tilde{x})$
$x(t_0) \leq \tilde{x}(t_0)$
$\implies x(t) \leq \tilde{x}(t) ,\forall t$
![[Pasted image 20260307153250.png]]

---
Ex.
$\dot{x}=-h(t)x^3=f(x,t)$
$h(t) \geq 1$
$\dot{x} \leq -x^3=g(x)$
$V(t,x) \equiv V(x)=\frac{1}{2}x^2$
$w_1,w_2$: Positive Definite
$w_1=w_2=\frac{1}{2} x^2$
$\dot{V}=x(-h(t)x^3)$
$=-h(t)x^4 \leq -w_3(x)$
$w_3=\frac{1}{2}x^4$ Positive Definite
$\implies x=0$ is uniformly asymptotically stable

---
Ex.
$\dot{x}=\frac{-x}{1+t}$
$x(t)=\frac{x(t_0)}{1+\frac{t-t_0}{1+t_0}}$
$|x(t)|\leq |x(t_0)|  \frac{1}{1+\frac{t-t_0}{1+t_0}}$
where $frac{1}{1+\frac{t-t_0}{1+t_0}}$ is not a class KL function
![[Pasted image 20260307153658.png]]

## Class 16
<u>Examples for utilizing comparison lemma</u>
$\dot{x}=-(1+x^2)x$
$x(0)=a$
$V=x^2$
$\dot{V}=2x\dot{x}=-2x^2-2xx^4$
$\leq -2x^2$
$=-2V$

$\dot{V} \leq 2V$
$V(t) \leq e^{-2t} V(0)$
$x^2(t) \leq e^{-2t} a^2$
$\implies |x(t)| \leq e^{-t} |a|$

Ex.
$\dot{x}=f(t,x)$
$=-(1+x^2)x+e^t$
$V=x^2$
$\dot{V}=2x \dot{x}$
$=-2x^2-2x^4+2xe^t$
$\leq -2V+2 \sqrt{V} e^t$
...(difficult to solve)

Alternate:
$V=|x(t)|=\sqrt{x^2(t)}$
$\frac{dV}{dt}=\frac{2x(t) \dot{x}(t)}{2\sqrt{x^2(t)}}$
$=\frac{x(t)[-(1+x^2)x+e^t]}{V}$
$=\frac{-x^2(1+x^2)}{\sqrt{x}}+\frac{x(t)e^t}{\sqrt{x^2}}$
$\leq -|x|(1+x^2)+e^t$
$\leq -|x|+e^t$
$=-V+e^t$
$\dot{V} \leq -V +e^t$
$V(t) \leq e^{-t} V(0)+\int_{0}^{t} e^{-(t-\tau)} e^t d\tau$
$\leq e^{-t} V(0)+e^\tau |_{0}^{t}$
$\leq e^{-t} V(0)+e^t-1$
$|x(t)| \leq e^{-t} |a|+e^t-1$

---
Ex.
$\dot{x}_1=-x_1+\frac{2x_2}{1+x_2^2}$
$\dot{x}_2=-x_2+\frac{2x_1}{1+x_1^2}$
$V=x_1^2+x_2^2$
$\dot{V}=x_1 \dot{x}_1+x_2 \dot{x}_2$
$=-x_1^2+\frac{2x_1 x_2}{1+x_2^2}-x_2^2+\frac{2x_1x_2}{1+x_1^2}$
$=-V+\frac{2x_1x_2}{1+x_2^2}+\frac{2x_1x_2}{1+x_1^2}$
$(x_1-x_2)^2=x_1^2+x_2^2-2x_1x_2\geq 0$
$\implies 2x_1x_2 \leq x_1^2 +x_2^2$
$4x_1x_2 \leq 2(x_1^2+x_2^2)$
$\dot{V} \leq -V+4x_1x_2$
$\leq -V+2V$
$\leq V$
$V(t) \leq e^{t} V(0)$
$x_1^2(t)+x_2^2(t) \leq e^t (x_1^2(0)+x_2^2(0))$

---
If $w_3(\cdot)$ is only semi-definite?
i.e., $w_3(x) \geq 0, \forall x \neq 0$
Thm: Suppose $w_1(x) \leq V(t,x) \leq w_2(x)$
$\dot{V}=\frac{\partial V}{\partial t}+\frac{\partial}{\partial x}f(t,x) \leq -w_3(x)$
$w_1,w_2$ are positive definite
$w_3$ is positive-semi definite
$w_1$ is radially unbounded
then, $w_3(x(t)) \rightarrow 0$ as $t\rightarrow \infty$

Ex.
$\dot{x}_1=-x_2+x_2$
$\dot{x}_2=-x_1$
$\dot{x}=Ax$
$A=\begin{bmatrix}-1 & 1 \\ -1 & 0\end{bmatrix}$
$A-\lambda I=\begin{bmatrix} -1-\lambda & 1 \\ -1 & -\lambda\end{bmatrix}$
$det(A-\lambda I)=\lambda(1+\lambda)+1$
$\lambda=\frac{-1 \pm \sqrt{1-4}}{2}$
$V=\frac{1}{2}x_1^2+\frac{1}{2}x_2^2$
$V=\frac{1}{2} x^T Px$
$P=I$
$\dot{V}=x_1 \dot{x}_1+x_2\dot{x}_2$
$=x_1(-x_1+x_2)+x_2(-x_1)$
$=-x_1^2$
$\dot{V}=0 | S=\{x:x_1=0\}$
$M=\{0\}$
LaSalle $\implies x(t)\rightarrow 0$

Ex.
$\dot{x}_1=-x_1+w(t)x_2$
$\dot{x}_2=-w(t)x_1$
$\dot{x}=A(t)x$
$=\begin{bmatrix} -1 & w(t) \\ w(t) & 0\end{bmatrix} x$
$V=\frac{1}{2} x_1^2+\frac{1}{2} x_2^2$
$\dot{V}=x_1 \dot{x}_1+x_2 \dot{x}_2$
$=x_1(-x_1+w(t)x_2)+x_2(-w(t)x_1)$
$=-x_1^2$
Impossible to have: $\leq -(f(x_1)+g(x_2))$ where $f(x_1), g(x_2)$ are positive definite

$x=0$ is uniformly stable
$w_3(x)=x_1^2$
$x_1 \rightarrow 0$ as $t \rightarrow \infty$

$\dot{x}=f(x,u(t))$

---
$\dot{x}=A(t)x$
Thm: $x=0$ is uniformly asymptotically stable if and only if:
$||\Phi(t,t_0)|| \leq k e^{-\lambda (t-t_))}$ for some $k>0, \lambda>0$
$x(t)=\Phi(t,t_0) x(t_0)$
$\dot{x}=Ax \implies x(t)=e^{A(t-t_0)} x(t_0)$
where $e^{A(t-t_0)}=\Phi(t,t_0)$

---
Recall
$\Phi(t,0)=\begin{bmatrix}e^{0.5t} \cos t & e^{-t} \sin t \\ e^{-0.5t} \sin t & e^{-t} \cos t\end{bmatrix}$
$||\Phi(t,0)||_p^2=e^{-2t}+e^{t} \cos^2 t+ e^{-t} \sin^2 t$
is not exponentially decaying
$\implies x=0$ is not uniformly stable

## Class 17
<u>LTV</u>:
$\dot{x}=A(t)x$
$x(t_0)=x_0$
$x(t)=\Phi(t,t_0)x(t_0)$
where $\Phi(t,t_0)$ is the state-transition matrix
<u>LTI</u>: Recall
$x(t)=e^{A(t-t_0)} x(t_0)$
where $e^{A(t-t_0)} = \Phi(t,t_0) \equiv \Phi(t-t_0)$

---
<u>LTV</u>: $\dot{x}=A(t)x$
Suppose $\dot{P}(t)=A(t) P(t)$
$P(t)$ is non-singular $\forall t \geq t_0$
$\Phi(t,t_0)=P(t) P^{-1}(t_0)$
$\Phi^{-1}(t,t_0)=[P(t) P^{-1}(t_0)]^{-1}$
$=P(t_0) P^{-1}(t)$
$=\Phi(t_0,t)$

<u>LTI</u>:
$\dot{x}=Ax$
$\dot{P}=AP$
$P=e^{At}$
$\Phi(t,t_0)=e^{At} e^{-A T_0}$
$=e^{A(t-t_0)}$

$P=2e^{At}$

---
$\Phi(t_0,t_0)=P(t_0) P^{-1}(t_0)=I$
$\frac{\partial}{\partial t} \Phi(t,t_0)=\frac{\partial}{\partial t} [P(t) P^{-1}(t_0)]$
$=\frac{\partial P(t)}{\partial t} P^{-1}(t_0)$
$=A(t) P(t) P^{-1} (t_0)$
==$\frac{\partial }{\partial t} \Phi(t,t_0)=A(t) \Phi(t,t_0)$==
$\frac{\partial}{\partial t_0}=\frac{\partial }{\partial t_0} [P(t) P^{-1}(t_0)]$
$=P(t) \frac{\partial}{\partial t_0} P^{-1}(t_0)$
$P^{-1}(t_0)=Q(t_0)$
$P(t_0) Q(t_0)=I$
$\frac{d}{dt_0} (P(t_0)Q(t_0))=0$
$P(t_0) \frac{d}{dt_0} Q(t_0)+\frac{d}{dt_0} P(t_0)Q(t_0)=0$
$\frac{d}{dt_0}Q(t_0)=-P^{-1}(t_0) A(t_0) P(t_0)Q(t_0)$
$=-P^{-1}(t_0) A(t_0)$
$\frac{\partial}{\partial t_0} \Phi(t,t_0)=-P(t) P^{-1}(t_0) A(t_0)$
==$\frac{\partial}{\partial t_0} \Phi(t,t_0)=-\Phi(t,t_0) A(t_0)$==

---
$\dot{x}=A(t)x$
$V(t,x)=x^T P(t) x$
<u>Recall sufficient conditions</u>:
- $W_1(x) \leq V(t,x) \leq W_2(x)$
Suppose $k_1 I \leq P(t) \leq k_2 I$ where $k_1,k_2 >0$
$W_1(x)=k_1 x^T x$
$W_2(x)=k_2x^Tx$
- $\dot{V}=\frac{d}{dt}[x^T P(t)x]$
$=\dot{x}^T P(t) x+x^T \dot{P}(t) x+x^T P(t) \dot{x}$
$=x^T A^{T}(t) P(t) x+x^T \dot{P}(t) x+x^T P(t) A(t)x$
$=x^T [A^T P+\dot{P} + PA]x$

Define: $\dot{P}(t)+A^T(t)P(t)+P(t)A(t)=-Q(t)$
$W_3(t)=k_3 x^Tx$   $\leftarrow k_3>0$
$Q(t) \geq k_3 I$
$-Q(t) \leq -k_3 I$
<u>Converse</u>
- Suppose $x=0$ is uniformly GAS
- $Q(t)$ is continuous and symmetric
- $\exists k_3,k_4>0$ s.t. $0\leq k_3 I \leq Q(t) \leq k_4 I$
$\implies \exists$ symmetric $P(t)$ s.t.
- $\dot{P}(t)+A^T(t)P(t)+P(t)A(t)=-Q(t)$
- $0 < k_1 I \leq P(t) \leq k_2 I$
Recall:
LTI: $P=\int_{0}^{\infty} e^{A^T \tau} Q e^{A\tau} d\tau$
LTV: $P(t)=\int_{t}^{\infty} \Phi^T(\tau, t) Q(\tau) \Phi(\tau,t)d\tau$

---
<u>Backstepping</u>:
Certain class of: $\dot{x}=f(x)+g(x)u$ where $x \in \mathbf{R}^n$
Scalar: $\dot{x}=f(x)+g(x)u$ where $x\in \mathbf{R}$
where $f(x), g(x), u$ are all scalar
$f(x)+g(x)u=-kx$ where $k>0$
$u(x)=-\frac{kx+f(x)}{g(x)}$ where $g(x) \neq 0$

---
Ex. $\dot{x}_1=x_1^2+u$
where $f(x)=x_1^2, g(x)=1$
$u=-(kx_1+x_1^2)$
$\dot{x}_1=x_1^2+x_2$
$\dot{x}_2=u$
$u \equiv u(x_1,x_2)$
$\implies \begin{bmatrix} x_1 \\ x_2\end{bmatrix}=\begin{bmatrix}0 \\ 0\end{bmatrix}$ GAS?

<u>Backstepping</u>
Treat $x_2$ as "virtual" input for the $x_1$ sub-system
$V(x_1)=\frac{1}{2} x_1^2$
$\alpha(x_1)=-k_1x_1-x_1^2$ where $k_1>0$
$z_2=x_2-\alpha(x_1)=x_2+k_1x_1+x_1^2$
$\dot{z}_2=\dot{x}_2-\dot{\alpha}$
$=u-\dot{\alpha}$
Choose $u=\alpha-\frac{\partial V_1}{\partial x_1}-x_1z_2$
$=-k_1 \dot{x}_1-2x_1 \dot{x}_1-x_1-k_2z_2$
$=-k_1(x_1^2+x_2)-2x_1(x_1^2+x_2)-x_1-k_2z_2$
$\tilde{V}=V_1(x_1)+\frac{1}{2} z_2^2$
$=\frac{1}{2} x_1^2+\frac{1}{2}z_2^2$
$\dot{\tilde{V}}=\frac{\partial V_1}{\partial x_1} \dot{x}_1+z_2 \dot{z}_2$
$\dot{x}_1=x_1^2+x_2$
$=x_1^2+z_2+\alpha$
$=-k_1x_1+z_2$
$\dot{\tilde{V}}=x_1(-k_1 x_1 +\dot{z}_2)+z_2(-x_1-k_2 z_2)$
$=-k_1x_1^2-k_2 z_2^2$
$\implies x_1 \rightarrow0$
$z_2 \rightarrow 0$
$x_2-\alpha(x_1) \rightarrow 0$
$x_2 \rightarrow \alpha(x_1)$
$\implies x_2 \rightarrow 0$ $(\because \alpha(x_1) \rightarrow 0)$
$\therefore \begin{bmatrix} x_1 \\ x_2\end{bmatrix}=0$ is GAS
The following is not always true:
$\dot{x}=f(x,\theta(t))$
$\theta(t) \rightarrow \theta^{\ast}; f(x,\theta^\ast)=-x$
$\implies x\rightarrow 0$ (NOT CORRECT)
if $\theta(t) \equiv \theta^{\ast}; f(x,\theta(t)) \equiv f(x,\theta^{\ast}) \equiv -x$
$\dot{x} \equiv -x$
$\implies \dot{x} \rightarrow 0$
Will not extend:
$\dot{x}_1=x_1^2+x_2+x_3$
$\dot{x}_2=x_2+x_3$
$\dot{x}_3=x_3+u$

## Class 18
Ex.
$\dot{x}_1=x_1^2-x_1^3+x_2=f_1(x_1,\alpha)+z_2$
$\dot{x}_2=x_3=\phi+z+3$
$\dot{x}_3=u$

---
$\alpha(x_1)=-x_1^2+x_1^3-x_1$
$V(x_1)=\frac{1}{2}x_1^2$

$\alpha(x_1)=-x_1^2$
$V(x_1)=\frac{1}{4} x_1^4$
$\dot{V}(x_1)=x_1^3 \dot{x}_1$
$=x_1^3(x_1^2-x_1^3-x_1^2)$
$=-x_1^6$

---
$z_2=x_2-\alpha(x_1)$
$\dot{z}_2=\dot{x}_2-\dot{\alpha}$
$V_2(x_1,z_2)=V_1(x_1)+\frac{1}{2} z_2^2$
$\dot{V}_2=\dot{V}_1+z_2 \dot{z}_2$
$=\frac{\partial V_1}{\partial x_1}[f_1(x_1,\alpha)+z_2]+z_2[\phi(x_1,x_2)-\dot{\alpha}]$
where $x_3$ is being treated as a virtual input $\phi$
$=\frac{\partial V_1}{\partial x_1}[f_1(x_1,\alpha)]+z_2 [\frac{\partial V_1}{\partial x_1}+\phi-\dot{\alpha}]$
$\phi(x_1,x_2)=\dot{\alpha}-z_2-\frac{\partial V_1}{\partial x_1}$
$z_3=x_3-\phi$
$\dot{z}_3=\dot{x}_3-\dot{\phi}$
$V_3(x_1,z_2,z_3)=V_2(x_1,z_2)+\frac{1}{2} z_3^2$
$\dot{V}_3=\dot{V}_2+z_3 \dot{z}_3$
$=\text{neg. def in in}$ $(x_1,z_2)$ $+z_2z_3+z_3(u-\dot{\phi})$
$=\text{neg. def in in}$ $(x_1,z_2)$ $+z_3(z_2+u-\dot{\phi})$
where $-z_3=z_2+u-\dot{\phi}$
$u=-z_2-z_3+\dot{\phi}$


Revisit
Ex.
$\dot{x}_1=x_1^2+x_2=x_1^2+\alpha+x_2-\alpha$
$=x_1^2+\alpha+z_2$
$=f_1(x_1,\alpha)+z_2$
$\dot{x}_2=u$
$\alpha(x_1)=-x_1^2-x_1$
$V_1(x_1)=\frac{1}{2} x_1^2$
$z_2=x_1-\alpha(x_1)$
$\dot{z}_2=u-\dot{\alpha}$
$V_c(x_1,z_1)=V_1(x_1)+\frac{1}{2} z_2^2$
$V_c=\dot{V}_1(x_1)+z_2 \dot{z}_2$
$=\frac{\partial V_1}{\partial x_1} (f_1(x,\alpha)+z_2)+z_2(u-\dot{\alpha})$
$=\frac{\partial V_1}{\partial x_1} f_1(x,\alpha)+z_2(\frac{\partial V_1}{\partial x_1}+u-\dot{\alpha})$
where $\frac{\partial V_1}{\partial x_1} f_1(x,\alpha)=-x_1^2; (\frac{\partial V_1}{\partial x_1}+u-\dot{\alpha})=-z_2$
$V_c=-x_1^2-z_2^2$
$\frac{\partial V_1}{\partial x_1}+u-\dot{\alpha}=-z_2$
$\implies u=\dot{\alpha} -z_2+\frac{\partial V_1}{\partial x_1}$
$=-2x_1\dot{x}_1-\dot{x}_1-x_2+\alpha(x_1)+x_1$
$=...$
$\implies \begin{bmatrix} x_1\\ x_2\end{bmatrix}=0$ is GAS
$\implies x_1 \rightarrow 0$
$z_2 \rightarrow 0$
$x_2-\alpha(x_1) \rightarrow 0$
$x_2\rightarrow \alpha(x_1)$
$\alpha(x_1) \rightarrow 0$
$x_2 \rightarrow 0$

---
Alternatively,
$\dot{x}_1=f_1(x,\alpha)+z_2$
$z_2 \equiv 0 \rightarrow x_1 \rightarrow 0$
$z_2 \rightarrow 0$
$\implies x_1 \rightarrow 0$ (NOT CORRECT)

$\dot{x}_1=\cos{x_1}+x_2$
$\dot{x}_2=u$
$\alpha(x_1)=-\cos{x_1}-x_1$
$z_2=x_2-\alpha$
$\begin{bmatrix}x_1 \\ z_2\end{bmatrix} \rightarrow 0$
$x_2 \rightarrow \alpha(0)=-1$

---
Backstepping can be applied recursively to systems of the form:
Strict feedback form:
$\dot{x}_1=f_1(x_1)+g_1(x_1)x_2$
$\dot{x}_2=f_2(x_1,x_2)+g(x_1,x_2)x_3$
$...$
$\dot{x}_n=f_n(x)+g_n(x)u$

Ex.
$\dot{x}_1=(x_1x_2-1)x_1^3+(x_1x_2+x_3^2-1)x_2$
where the term $x_3^2$ is not in strict feedback form
$\dot{x}_2=x_3$
$\dot{x}_3=u$

---
$\dot{x}_1=(x_1x_2-1)x_1^3+(x_1x_2-1)x_1$
$=f_1(x_1)+g_1(x_1)x_2$
$=x_1^4x_2-x_1^3+x_1^2x_2-x_1$
$=(-x_1^3-x_1)+(x_1^4+x_1^2)x_2$
where $f_1=(-x_1^3-x_1), g_1=(x_1^4+x_1^2)$

---
$\dot{x}_1=(x_1x_2-1)x_1^3+(x_1x_2-1)x_1+u$
$\dot{x}_2=x_3$
$\dot{x}_3=x_2$
$y_1=x_2$
$y_2=x_3$
$y_3=x_1$
$\dot{y}_1=y_2$
$\dot{y}_2=y_1$
$\dot{y}_3=()u$ (INVALID)

---
![[Pasted image 20260327160944.png]]
$x_1 \in \mathbf{R}^{n1}, x_2 \in \mathbf{R}^{n2}$
- If $x_1=0$ is GAS for $\dot{x}_1=f_1(x_1,0)$
- If $x_2=0$ is GAS for $\dot{x}_2=f_2(x_2)$
$(x_1,x_2)=0$ is GAS for the interconnection? (NO)

Ex.
$\dot{x}_1=-x_1+x_1^2x_2$
$\dot{x}_2=-x_2$
Exhibit finite escape time
$\dot{x}_1=-x_1+x_1^2 u$ ($u$ exponentially decaying)
$u \equiv \epsilon$
$\dot{x}_1=-x_1+x_1^2 \epsilon$
$=x_1(\epsilon x_1-1)$
$\frac{dx}{x(\epsilon x_1-1)}=dt$
$dx[\frac{1}{\epsilon x-1}-\frac{1}{\epsilon x}]=\frac{dt}{\epsilon}$
$\frac{\ln |\epsilon x-1|}{\epsilon}|_{x_0}^{x}-\frac{\ln|\epsilon x|}{\epsilon}|_{x_0}^{x}=\frac{t}{\epsilon}$
$\frac{\epsilon x-1}{\epsilon x_0-1} \frac{\epsilon x_0}{\epsilon x}=e^t$
$\frac{\epsilon x-1}{\epsilon x}=\frac{\epsilon x_0-1}{\epsilon x_0} e^t$
$x_0=\frac{1.1}{\epsilon}$
$\frac{\epsilon x-1}{\epsilon x}=\frac{0.1}{1.1} e^t=\frac{1}{11}e^t$
$\frac{-1}{\epsilon x}=\frac{e^t-11}{11}$
$x=-\frac{11}{\epsilon(e^t-11)}=\frac{11}{\epsilon(11-e^t)}$
Finite escape time

---
<u>Input-to-state Stability</u>
The system $\dot{x}=f(x,u), f(0,0)=0$ is said to be input-to-state (ISS) stable if:
$|x(t)| \leq \beta(|x(0)|,t) + \gamma(sup_{0 \leq \tau \leq t} |u(\tau)|)$
where $\beta$ is class KL function
$\gamma$ is class K function
- If $u \equiv 0$
$\implies |x(t)| \leq \beta(|x(0)|,t) \implies x=0$ GAS
ISS $\implies$ GAS
- If $u(t) \rightarrow 0$
$x=0$ is GAS

Ex.
$\dot{x}=-x^r+x^s u$
$r:$ odd integer $\implies$ ISS
$r>s$

## Class 19
$x_1=\begin{bmatrix} x_{1,1} \\ ... \\ x_{1,n}\end{bmatrix}$
![[Pasted image 20260327163213.png]]
$\dot{x}_2=f(0,x_2)$
$x_2=0$ is GAS
$\dot{x}=Ax+Bu$
- If $A$ is Hurwitz, then $\dot{x}=Ax+Bu$ is ISS

$x(t)=e^{At}x_0+\int_{0}^{t} e^{A(t-\tau)} B u(\tau) d\tau$
$|x(t)| \leq |e^{At}x_0|+\int_{0}^{t} |e^{A(t-\tau)} B u(\tau)|d\tau$
$\leq |e^{At}||x_0|+|B| \sup_{\tau \in [0,t]} u(\tau) \int_{0}^{t} |e^{A(t-\tau)}|d\tau$

---
If $A$ is Hurwitz, then there exist $k>0, \lambda>0$ s.t.
$|e^{At}| \leq k e^{-\lambda t}$               ($\forall t \geq 0$)
$A=VJW$
$e^{At}=Ve^{Jt}W$
$|e^{At}| \leq |V||e^{Jt}||W|$
$J=\begin{bmatrix}-\lambda_1 & ... &0 \\ ... & ... & ... \\ 0 & ... & -\lambda_n \end{bmatrix}; e^{Jt}=\begin{bmatrix}e^{-\lambda_1 t} & ... &0 \\ ... & ... & ... \\ 0 & ... & e^{-\lambda_n t} \end{bmatrix}$
$|e^{Jt}|=e^{\lambda_1 t}$

---
$|x(t)|\leq k e^{-\lambda t} |x_0|+|B| sup_{\tau \in [0,t]} u(\tau) k \int_{0}^{t} e^{-\lambda(t-\tau)}d\tau$
$=k e^{-\lambda t} |x_0|+\frac{|B|k}{\lambda}sup_{\tau \in [0,t]} u(\tau) k e^{-\lambda (t-\tau)}|_{0}^{t}$
$|x(t)| \leq  k e^{-\lambda t} |x_0|+\frac{|B|k}{\lambda}sup_{\tau \in [0,t]} u(\tau) k (1-e^{-\lambda t})$
$|x(t)| \leq  k e^{-\lambda t} |x_0|+\frac{|B|k}{\lambda}sup_{\tau \in [0,t]} u(\tau) k$
v.s.
ISS: $|x(t)| \leq \beta(|x(0)|,t)+\gamma(\sup_{\tau \in [0,t]} u(\tau))$
$\beta(\cdot)=ke^{-\lambda t} |x_0|$
$\gamma(\cdot)=\frac{|B|k}{\lambda}(\cdot)$

Thm:
$V$ is $C^1$
- $\alpha_1(||x||) \leq V(x) \leq \alpha_2(||x||)$
- $\frac{\partial V}{\partial x}f(x,u) \leq -W_3(x) \forall ||x||\geq \rho(||u||)>0$

where $\dot{V}=\frac{\partial V}{\partial x}f(x,u)$
$\alpha_1,\alpha_2$ are class $K_{\infty}$ functions
$\rho$ is class K function
$W_3$ is positive definite
$\implies \dot{x}=f(x,u)$ is ISS
$\gamma=\alpha_1^{-1} \circ \alpha_2 \circ \rho$
$\gamma$ is called the ISS gain

---
Ex.
$\dot{x}=-x^3+u$
$V(x)=\frac{1}{2}x^2$
$\alpha_1=\alpha_2=\frac{1}{2}x^2$
$\dot{V}=x \dot{x}$
$=x(-x^3+u)$
$=-x^4+xu \leq -W_3(x) \forall ||x|| \geq \rho(||u||)$
$=-\frac{1}{2} x^4-\frac{1}{2}x^4+xu$

---
$-\frac{1}{2}x^4+xu \leq 0 \leftarrow |x|^3 \geq 2|u|$
i.e., $|x| \geq (2|u|)^{\frac{1}{3}}$
$\rho(r)=(2r)^{\frac{1}{3}}$
$W_3(r)=-\frac{1}{2} r^4$
$\alpha_1(r)=\frac{1}{2}r^2$
$\alpha_2(r)=\frac{1}{2}r^2$
$\alpha_1^{-1} \circ \alpha_2 =I$
$\gamma=\rho=(2r)^{\frac{1}{3}}$

Ex.
$\dot{x}=-x^r+x^s u$
$r:$ odd integer $\implies$ ISS
$r >s$
$V=\frac{1}{2}x^2$
$\dot{V}=x \dot{x}$
$=x(-x^r+x^s u)$
$=-x^{r+1}+x^{s+1}u$
$=-\frac{1}{2} x^{r+1}-\frac{1}{2} x^{r+1}+x^{s+1}u$
where $-\frac{1}{2} x^{r+1} =-W_3(x)$
$-\frac{1}{2} x^{r+1}+x^{s+1}u \leq 0$
$\implies |x|^{r-s} \geq 2|u|$
i.e., $|x| \geq (2|u|)^{\frac{1}{r-s}}$
$\rho(s)=(2r)^{\frac{1}{r-s}}$

Ex.
$\dot{x}=-x^3$
$x(t)=sgn x_0 \sqrt{\frac{x_0^2}{1+2tx_0^2}}$
$x=0$ GAS but not exponentially stable
$x_0=1$
$\implies x(t)=\sqrt{\frac{1}{1+2t}}$
$\dot{x}=-2x$
$x(t)=e^{-2t} x_0$

$\dot{x}=Ax$
$x(t)=e^{At}x_0$
$|x(t)| \leq |e^{At}| |x_0|$
$\leq  k e^{-\lambda t} |x_0|$

---
$\dot{x}=f(x), f(0)=0$
$x=0$ is exponentially stable if 
$|x(t)| \leq k |x_0| e^{-\lambda t}$ for some $k>0,\lambda>0$

Thm: $\dot{x}=f(x,u)$
- $f(x,u)$ is "globally" Lipschitz in $(x,u)$
- $x=0$ is globally exponentially stable (GES) for $\dot{x}=f(x,0)$

$\implies \dot{x}=f(x,u)$ is GES

---
Sufficient condition for GES:
-(GAS)
- $W_1(x) \leq V(x) \leq W_2(x)$ ($W_1,W_2$ are positive definite)
- $\dot{V}(x) \leq -W_3(x)$ ($W_3$ is positive definite)
- $W_1$ is radially unbounded
+
- $W_i=k_i |x|^a$ where $i=1,2,3; k_1,k_2,k_3, a>0$

Then $x=0$ is GES

---
Ex.
$\dot{x}=-3x+(1+x^2)u=f(x,u)$
$x=0$ is GES for $\dot{x}=f(x,0)=-3x$
$f(x,u)$ is NOT globally Lipschitz
ISS inconclusive

---
$V=\frac{1}{2}x^2$
$\dot{V}=x \dot{x}$
$=x(-3x+(1+x^2)u)$
$=-3x^2+xu+x^3u$
$=-x^2+(-x^2+xu)+(-x^2+x^3u)$
- $-x^2+xu \leq 0 \leftarrow |x| \geq |u|$
- $-x^2+x^3u \leq 0 \leftarrow |x||u| \leq 1$ (NO)

---
Ex.
$\dot{x}=-\frac{x}{1+x^2}+u=f(x,u)$
$\dot{x}=-\frac{x}{1+x^2}$
$V=\frac{1}{2}x^2$
$\dot{V}=x\dot{x}$
$=-\frac{x^2}{1+x^2}$
NOT globally exponentially stable
$|f(x,u)-f(\tilde{x}, \tilde{u})| \leq |\frac{x}{1+x^2} -\frac{\tilde{x}}{1+\tilde{x}^2}|+|u-\tilde{u}|$
$\leq |x-\tilde{x}|+|u-\tilde{u}|$
$=|\begin{bmatrix} x \\ u \end{bmatrix} - \begin{bmatrix} \tilde{x}\\ \tilde{u}\end{bmatrix}|$
$L=1$
$V=\frac{1}{2}x^2$
$\dot{V}=x\dot{x}$
$=x(-\frac{x}{1+x^2}+u)$
$=-\frac{x^2}{1+x^2}+xu$
$=-\frac{1}{2} \frac{x^2}{1+x^2}-\frac{1}{2} \frac{x^2}{1+x^2}+xu$

---

$-\frac{1}{2} \frac{x^2}{1+x^2}+xu \leq 0 \leftarrow 1+ |x|^2 \leq \frac{x}{u}$


# Class 20

# Class 21

# Class 22

LMI
$x_0F_0+x_1F_1+...+x_n F_n \geq0$
$F_0,F_1,...F_n \geq 0$ (given)
Required to find $x_1,...,x_n \in \mathbf{R}$ s.t.

$A^TP+PA \leq -Q$
- satisfied with $=$
- $\exists P$ s.t. $A^TP+PA :=-\tilde{Q} <-Q$
	$\tilde{Q} >0$
$Q-\tilde{Q} \leq 0$
i.e., $\tilde{Q} \geq Q$
$A^TP+PA \leq -Q$
$A=\begin{bmatrix} a_{11} & a_{12} \\ a_{21} & a_{22}\end{bmatrix}$
Find $P>0$ s.t. $A^TP+PA \leq -Q$
$\implies$ LMI
$\begin{bmatrix}P&0\\0&-A^TP-PA-Q\end{bmatrix} \geq 0$

---
Fact:
$X=\begin{bmatrix} A& B \\ B^T & C\end{bmatrix} \in \mathbf{R}^{n \times m}$
If $A>0$ then $x \geq 0$ if and only if $C-B^TA^{-1}B \geq 0$
where $C-B^TA^{-1}B$ is the Schur complement

---
$-A^TP-PA-Q\geq 0$ v.s. $F_0+x_1F_1+...+x_nF_n \geq 0$
$\downarrow$ LMI?
$A=\begin{bmatrix} a_{11} & a_{12} \\ a_{21} & a_{22}\end{bmatrix}$
$P=\begin{bmatrix} p_{11} & p_{12} \\ p_{12} & p_{22}\end{bmatrix}$
$A^TP=\begin{bmatrix} a_{11}p_{11}+a_{21}p_{12} & a_{11}p_{12}+a_{21}p_{22}\\ a_{12}p_{11}+a_{22}p_{12} & a_{12}p_{12}+a_{22}p_{22}\end{bmatrix}$
$PA=\begin{bmatrix}p_{11}a_{11}+p_{12}a_{21} & p_{11}a_{12}+p_{12}a_{22}\\ p_{12}a_{11}+p_{22}a_{21} & p_{12}a_{12}+p_{22}a_{22}\end{bmatrix}$
$A^TP+PA=p_{11}(\begin{bmatrix}a_{11}&0\\ a_{12}&0\end{bmatrix}+\begin{bmatrix}a_{12} & a_{12}\\ 0 & 0\end{bmatrix})+p_{12}(\begin{bmatrix}a_{21}&a_{11}\\ a_{22}&a_{12}\end{bmatrix}+\begin{bmatrix}a_{21}&a_{22}\\ a_{11} & a_{12}\end{bmatrix})+p_{22}(\begin{bmatrix}0&a_{21} \\ 0& a_{22}\end{bmatrix}+\begin{bmatrix}0 & 0\\ a_{21}& a_{22}\end{bmatrix})$
where $\begin{bmatrix}a_{11}&0\\ a_{12}&0\end{bmatrix}+\begin{bmatrix}a_{12} & a_{12}\\ 0 & 0\end{bmatrix}=-F_1, \begin{bmatrix}a_{21}&a_{11}\\ a_{22}&a_{12}\end{bmatrix}+\begin{bmatrix}a_{21}&a_{22}\\ a_{11} & a_{12}\end{bmatrix}=-F_2,\begin{bmatrix}0&a_{21} \\ 0& a_{22}\end{bmatrix}+\begin{bmatrix}0 & 0\\ a_{21}& a_{22}\end{bmatrix}=-F_3$
$\begin{bmatrix} P& 0 \\ 0& -A^TP-PA-Q\end{bmatrix}=\tilde{F_0}+p_11\tilde{F_1}+p_12\tilde{F_2}+p22\tilde{F_3}$
$\tilde{F_0}=\begin{bmatrix}0& 0\\ 0& -Q\end{bmatrix}$
$\tilde{F_1}=\begin{bmatrix} 1 & 0 & 0 \\ 0& 0 & 0 \\ 0&0& -F_1\end{bmatrix}$
$\tilde{F_2}=\begin{bmatrix} 0& 1 & 0 \\ 1& 0& 0\\ 0&0&-F_2\end{bmatrix}$
$\tilde{F_3}=\begin{bmatrix}0&0&0\\ 0&1&0\\ 0& 0 &-F_3\end{bmatrix}$

Ex.
$||Ax-b||\leq \gamma$
Given $A,b, \gamma$
$(Ax-b)^T (Ax-b)\leq \gamma^2$
$\implies \gamma^2-(Ax-b)^T (Ax-b) \geq 0$
$\gamma^2-(Ax-b)^T (Ax-b)$ Schur Complement
if and only if 
v.s. 
$C-B^TA^{-1}B$
$\begin{bmatrix}A&B\\ B^T &C\end{bmatrix} \geq 0$
$\begin{bmatrix} I & (Ax-b) \\ (Ax-b)^T & \gamma^2\end{bmatrix}$
LMI

---
<u>Linearization</u> 
Ex.
$\dot{x}_1=x_2$
$\dot{x}_2=-x_1+\epsilon(1-x_1^2)x_2+u, \epsilon >0$
(Van der Pol Equation)
$y=x_1$
$\dot{y}=\dot{x}_1=x_2$
$\ddot{y}=\dot{x}_2=-x_1+\epsilon (1-x_1^2)x_2+u$
$u=x_1-\epsilon(1-x_1^2)x_2+v$
$\ddot{y}=v$
$x_1=\zeta_1=y$
$x_2=\zeta_2=\dot{y}$
$\dot{\zeta}_1=\zeta_2$
$\dot{\zeta}_2=v$
$\begin{bmatrix} \dot{\zeta}_1 \\ \dot{\zeta}_2\end{bmatrix}=\begin{bmatrix} 0 & 1\\ 0& 0\end{bmatrix}\begin{bmatrix} \zeta_1 \\ \zeta_2\end{bmatrix}+\begin{bmatrix}0\\ 1 \end{bmatrix}v$
where $\begin{bmatrix} 0 & 1\\ 0& 0\end{bmatrix}=A, \begin{bmatrix}0\\ 1 \end{bmatrix}=B$
$v=k_1 \zeta_1+k_2 \zeta_2$
$=k_1x_1+k_2x_2$
$\begin{bmatrix} B & AB\end{bmatrix}=\begin{bmatrix} 0& 1 \\ 1&0\end{bmatrix}$

One can design $k_1,k_2$ s.t.
$\zeta_1=0, \zeta_2=0$ $(x_1,x_2)=(0,0)$ is GAS

---
Now suppose $y=x_2$
$\dot{y}=-x_1+\epsilon (1-x_1^2)x_2+u, \epsilon >0$
$u=x_1-\epsilon(1-x_1^2)x_2+v$
$\zeta_1=y=x_2$
$\dot{\zeta}_2=v$
$\dot{y}=v$
$v=-k_1\zeta_1$
$\implies \zeta_1=0$ is GAS
$\dot{x}_1=x_2$
$\dot{x}_2=-k_1x_2$

zero dynamics: $x_2=0$
$\implies \dot{x}_1=0$
$x_1=0$ is not GAS
$\implies$ non-minimum phase

---
Ex.
$\dot{x}_1=x_2$
$\dot{x}_2=\alpha x_3+u$
$\dot{x}_3=\beta x_3-u$
$y=x_1$
$A=\begin{bmatrix} 0 & 1 & 0 \\ 0& 0& \alpha \\ 0& 0 &\beta\end{bmatrix}$
$B=\begin{bmatrix} 0\\ 1 \\-1\end{bmatrix}$
$C=\begin{bmatrix} 1 & 0 & 0\end{bmatrix}$
$H(s)=C(SI-A)^{-1} B=\frac{s-(\alpha+\beta)}{s^2(s-\beta)}$
relative degree= degree of denominator -degree of numerator $=3-1=2$
$\dot{y}=\dot{x}_1=x_2$
$\ddot{y}=\dot{x}_2=\alpha x_3+u$
$\zeta_1=x_1$
$\zeta_2=x_2$
$u=-\alpha x_3+v$
$v=-k_1x_1-k_2x_2$
$\implies \begin{bmatrix} \zeta_1 \\ \zeta_2\end{bmatrix}=0$
$\dot{x}_3=\beta x_3+\alpha x_3-v$
$=(\alpha+\beta)x_3+k_1x_1+k_2x_2$

---
Ex.
$\dot{x}_1=x_2$
$\dot{x}_2=-x_1^3+u$
$y=x_1$
$\dot{y}=\dot{x}_1=x_2$
$\ddot{y}=\dot{x}_2=-x_1^3+u$
Relative degree$=2$

Ex.
$\dot{x}_1=x_2+x_3^3$
$\dot{x}_2=x_3$
$\dot{x}_3=u$
$y=x_1$
$\dot{y}=\dot{x}_1=x_2+x_3^3$
$\ddot{y}=\dot{x}_2+3x_3^2 \dot{x}_3$
$=x_3+3x_3^2u$
Does not have a well-defined relative degree around $x=0$

Relative degree$=r\leq n$
$\dot{x}=f(x,u)$
$y=h(x)$
$\dot{y}=\frac{dy}{dt}h(x)=\frac{\partial h(x)}{\partial x} \dot{x}=\frac{\partial h(x)}{\partial x} f \triangleq L_f h$
$y^r=v$
$\dot{\zeta}_1=\zeta_2$
$...$
$\dot{\zeta^r}=v$
$h(x)=0=\zeta_1=y$
$L_fh(x)=0=\zeta_2=\dot{y}$
$...$
$L_f^{r-1}h(x)=0=\zeta_r=y^{r-1}$
$v=-k_1\zeta_1...-k_r\zeta_r$
Q: Does this controller ensure that $x=0$ is GAS?
$(n-r)$ dimensional manifold:
$h(x)=0$
$L_fh(x)=0$
$...$
$L_f^{r-1}h(x)=0$
Dynamics restricted to this manifold is called zero dynamics

Ex.
![[Pasted image 20260416153127.png]]
$\ddot{y}=\frac{1}{\frac{M}{m}+\sin^2\theta}(\frac{u}{m}+\dot{\theta}^2l \sin\theta-g \sin\theta \cos\theta)$
$\ddot{\theta}=\frac{1}{l(\frac{M}{m}+\sin^2\theta)}(-\frac{u}{m}\cos\theta-\dot{\theta}^2l\cos\theta\sin\theta+\frac{M+m}{m}g\sin\theta)$

# Class 23


# Class 24

# Class 25

# Class 26

# Class27
Ex.
$\dot{x}_1=x_2$
$\dot{x}_2=\theta x_1^2+U$
where $\theta \in [0.9,1.1]$
$\theta=1+\Delta$
$\Delta \in [-0.1,0.1]$

$s=x_1+x_2$
$\dot{s}=\dot{x}_1+\dot{x}_2$
$\dot{s}=x_2+\theta x_1^2 +u$
where $\delta(x)=x_2+\theta x_1^2$
$|\delta(x)|=|x_2|+1.1 |x_1|^2=\rho(x)$
$u=-(\rho(x)+\rho_0)sgn(s)$
where $\rho_0>0$
$s \rightarrow 0$ in finite time

$\dot{s}=x_2+\theta x_1^2+u$
where $\theta=1+\Delta$
$\dot{s}=x_2+x_1^2+\Delta x_1^2+u$
$u=-x_2-x_1^2+v$
$\implies \dot{s}=\Delta x_1^2 +v$
where $\delta(x)=\Delta x_1^2$
$|\delta(x)|\leq 0.1 x_1^2$
$v=-(0.1 x_1^2+\rho_0)sgn(s)$

Without centering: $u=-(|x_2|+1.1x_1^2+\rho_0) sgn(s)$
With centering: $u=-x_1-x_1^2-(0.1x_1^2+\rho_0)sgn(s)$ (less chattering)


Ex.
$\dot{x}_1=x_1x_2$
$\dot{x}_2=\theta x_1^2+u$
where $|\theta| \leq 2$
$\alpha(x_1)=-x_1^2$
$s=x_2-\alpha(x_1)$
$=x_2+x_1^2$
$\dot{s}=\dot{x}_2+2x_1 \dot{x}_1$
$=\theta x_1^2+u+2x_1^2x_2$
$=2x_1^2x_2+\theta x_1^2+u$
$u=-2x_1^2 x_2-(2x_1^2+\rho_0)sgn(s)$ where $\rho_0>0$
$s \rightarrow 0$ in finite time
