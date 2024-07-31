## Classifier for Probability Estimation - K-NN, Parzen Window and Kernels
***Parzen Window***: 
Before training we can “filter” the data using a function, for example using the **hypercube function** that selects only the data in a specific region, an hypercube, wide $h_n$ , with $d$ dimensions (so its volume will be $V_n = (h_n)^d$ ).
We have defined the “***window function***” or “***kernel***” as:
$$
\varphi(\underline{u}) = 
\left\{ \begin{array}{c}
\kern5px 1 & \kern5px |u_j| \le \frac{1}{2} \kern15px \forall \kern1px j = 1 ,\ 2 ,\ \ldots ,\ d
\\
\kern5px 0 &
\end{array}\right.
$$
The **kernel** $\varphi\left( \frac{\underline{x_0}-\underline{x_i}}{h_n} \right)$ is a kernel having value $1$ only within the hypercube centered in $\underline{x_0}$ and having edge $h_n$, the **number of data** in this hypercube ($k_n$) is:
$$
k_n = \sum_{i=1}^{n} \ \varphi\left( \frac{\underline{x_0}-\underline{x_i}}{h_n} \right)
$$
As we have defined before the estimate $p_n(\underline{x_0})$ of the **unknown pdf $p(\cdot)$** is $\frac{k_n}{n \ V_n}$ , then:
$$
p_n(\underline{x_0}) = \frac{1}{n \kern2px V_n} \cdot \sum_{i=1}^{n} \ \varphi\left( \frac{\underline{x_0}-\underline{x_i}}{h_n} \right)

$$
> **NOTE**:
> We have defined $\varphi(\cdot)$ as the *hypercube function* but this form is equivalent for all **window functions**.

<br>


For example one common choice of a kernel is the **Gaussian Kernel**:
$$
\varphi(\underline{u}) = \operatorname{N}(\underline{u}  \, ;\ \underline {0} \, ,\ 1)
$$
- $\operatorname{N}(\cdot)$ : **Gaussian pdf**.
- $\underline{u}$ : vector of variables, this is a *multivariate gaussian distribution*
- $\underline{0}$ : mean
- $1$ : variance

<br>

***Sufficient Condition for Asserting that $p_n(\cdot)$ is a PDF*** :
1. $\varphi(\underline{u}) \ge 0 \kern15px \forall \kern2px \underline{u} \in \mathbb{R}^d$
2. $\int \varphi(\underline{u}) \ d\underline{u}  = 1$

> **NOTE**:
> Also, no matter the type of function $\varphi(\cdot)$, we can just take $h_n = \frac{\alpha}{\sqrt{n}}$ where $\alpha \in \mathbb{R}$ is an hyperparameter decided arbitrarily, and we can guarantee, as seen in the previous lecture, that the estimated pdf $p_n(\underline{x})$ will converge to the actual pdf $p(\underline{x})$, as the number of data $n \to \infty$ .

<br>

***Dirac’s Window Function***:
Let us define:
$$
\delta_n(\underline{x}) = \frac{1}{V_n} \cdot \operatorname{\varphi} \left(\frac{\underline{x}}{h_n}\right)
$$
Notice how:
- If $h_n$ is **big** the function $\delta_n(\underline{x} - \underline{x_i})$ is a very smooth function, having small variation and representing a rectangle centered in $\underline{x_i}$ high $\frac{1}{V_n}$ and total area equal to $1$.
- if $h_n$ is **really small**, $h_n \to 0$ , than $\delta_n(\underline{x} - \underline{x_i})$ is a **Dirac’s Delta** centered in $\underline{x_i}$.

> **NOTE**:
> This is a useful example to understand how a different **kernel** can impact the quality of the estimate $p_n(\underline{x})$.

<br>

***$k_n$-Nearest Neighbour*** :
Given that $h_n = \frac{\alpha}{\sqrt{n}}$ we could have some problems:
- If $\alpha$ is too small ⇒ $p_n(\cdot) = 0$ .
- If $\alpha$ is too big ⇒ $p_n(\cdot) = \operatorname{E}[ \kern3px p(\cdot) \kern1px ]$ .

We can solve this problem generalizing the value of $\alpha$, first we want to assert that:
1. $\lim_{n \to \infty} k_n = \infty$ 
1. $\lim_{n \to \infty} \frac{k_n}{n} = 0$ 

A possible solution to this problem is taking $k_n = \sqrt{n}$, such that:
$$
p_n(\underline{x_0}) = \frac{k_n}{n \ V_n} = \frac{1}{\sqrt{n} \ V_n}
$$
Now instead of deciding the Volume $V_n$ we create it this way:
1. Chose our center $\underline{x_0}$
2. Create an hypersphere of dimension $d$ around $\underline{x_0}$
3. Let the sphere expand until it includes $k_n = \sqrt{n}$ data.
4. Calculate the volume $V_n$ of this hypersphere.

To have more flexibility we can define $k_n = \alpha \cdot \sqrt{n}$ where $\alpha \in \mathbb{R}$ is an **hyperparameter** decided arbitrarily.


---
# Original Files
![[Pasted image 20220817102315.png]]

Where:
- $n$ : number of hypercubes.
- $R_n$ : hypercube (cube wide $h_n$ with dimension $d$).
- $V_n$ : Volume of the hypercube, $V_n= (h_n)^d$
- $\varphi(x)$: **window function**, or **kernel**
- $k_n$ : number of data given, in this case the sum of all the $n$ hypercubes' volumes.
- $p(\underline{x})$ : **multivariate pdf** where $\underline{x}$ is a vector.
- $p_n(\underline{x})$ : $n$-th estimation of the pdf $p(\underline{x})$.

![[Pasted image 20220817103629.png]]

> **NOTE**:
> **Gaussian Kernel** : $\varphi(\underline{u}) = \operatorname{N}(\underline{u} \ ; \ \underline{0} \ , \ 1)$
> $\underline{u}$ : vector of variables, this is a *multivariate gaussian distribution*
> $\underline{0}$ : mean
> $1$ : variance

![[Pasted image 20220817104105.png]]
![[Pasted image 20220817104547.png]]
Where: 
- $h_1$ : hyperparameter, width of the hypercubes.
- $n$ : hyperparameter, number of hypercubes we wish to take.

If we change the $p(x)$
![[Pasted image 20220817105223.png]]

----
![[Pasted image 20220817105313.png]]
![[Pasted image 20220817105453.png]]
