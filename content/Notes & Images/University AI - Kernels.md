- [[University AI - Differences Between K-NN, Parzen Window and Kernel Classifiers]]

---
## Examples of Kernels:
##### Hypercube Function
$$
\varphi(\underline{u}) = 
\left\{ \begin{array}{c}
\kern5px 1 & \kern5px |u_j| \le \frac{1}{2} \kern15px \forall \kern1px j = 1 ,\ 2 ,\ \ldots ,\ d
\\
\kern5px 0 &
\end{array}\right.
$$
The **kernel** $\varphi\left( \frac{\underline{x_0}-\underline{x_i}}{h_n} \right)$ is a kernel having value $1$ only within the hypercube centred in $\underline{x_0}$ and having edge $h_n$, the **number of data** in this hypercube ($k_n$) is:
$$
k_n = \sum_{i=1}^{n} \ \varphi\left( \frac{\underline{x_0}-\underline{x_i}}{h_n} \right)
$$
<br>
<br>

##### Gaussian Kernel
*One of the most common choices for a kernel*.
$$
\varphi(\underline{u}) = \operatorname{N}(\underline{u}  \, ;\ \underline {0} \, ,\ 1)
$$
Where:	
- $\operatorname{N}(\cdot)$ : **Gaussian pdf**.
- $\underline{u}$ : vector of variables, this is a *multivariate gaussian distribution*
- $\underline{0}$ : mean
- $1$ : variance

<br>
<br>


##### Dirac’s Window Function
Let us define:
$$
\delta_n(\underline{x}) = \frac{1}{V_n} \cdot \operatorname{\varphi} \left(\frac{\underline{x}}{h_n}\right)
$$
Notice how:
- If $h_n$ is **big** the function $\delta_n(\underline{x} - \underline{x_i})$ is a very smooth function, having small variation and representing a rectangle centered in $\underline{x_i}$ high $\frac{1}{V_n}$ and total area equal to $1$.
- if $h_n$ is **really small**, $h_n \to 0$ , than $\delta_n(\underline{x} - \underline{x_i})$ is a **Dirac’s Delta** centered in $\underline{x_i}$.

> **NOTE**:
> This is a useful example to understand how a different **kernel** can impact the quality of the estimate $p_n(\underline{x})$.

