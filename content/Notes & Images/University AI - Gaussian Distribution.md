## Gaussian Distribution
***Gaussian or Normal Distributions***:
$$
p(x) = 
\frac{1}{\sigma\kern2px\sqrt{2\pi}} 
\operatorname{exp}\left\{
	-\frac{1}{2}\left(
		\frac{x - \mu}{\sigma}
	\right)^2
\right\}
$$
Where:
- $\mu$ : **mean** of the distribution
- $\sigma$ : **variance** of the distribution

<br>

***Multivariate Gaussian Distributions***:
$$
p(x) = 
\frac{1}{|\Sigma|^{1/2}\kern3px\left(2\pi\right)^{d/2}} 
\operatorname{exp}\left\{
	-\frac{1}{2} \kern1px
	\left(x - \mu\right)^T \kern4px
	\Sigma^{-1} \kern0px
	\left(x - \mu\right)
\right\}
$$
Where:
- $\mu$ : **vector mean**
- $\sigma$ : **variance matrix**

<br>

***Definition of Mean and Variance***:
$$
\begin{align}
& \operatorname{E}[x] =  \int_{-\infty}^{+\infty} x \kern3px p(x) \kern3px dx = \mu
\\
& \operatorname{Var}[x] \triangleq  \operatorname{E}[\left(x - \mu\right)^2] =  \int_{-\infty}^{+\infty} \left(x - \mu\right)^2 \kern3px p(x) \kern3px dx = \sigma
\end{align}
$$
***Definition of Vector Mean and Variance Matrix (Multivariate)***:
$$
\begin{align}
& \operatorname{E}[ \kern1px \underline{x} \kern1px ] = \underline{\mu}
\\
& \operatorname{E}[ \kern2px (\underline{x} - \underline{\mu})(\underline{x} - \underline{\mu})^T \kern4px ] = \Sigma 
\end{align}
$$

<br>

***Distribution of Gaussian Data***:
If we plot the **eigenvector** of the **variance matrix** $\Sigma$ in a cartesian plane we obtain:
![[Pasted image 20220809153050 - Plot.png]]
- The quantity $(\underline{x} - \underline{\mu})^T \kern4px \Sigma^{-1} \kern0px (\underline{x} - \underline{\mu})$ is known as **Mahalanobis distance** between $\underline{x}$ and $\underline{\mu}$ , the hyper-ellipsoid we see in the graph are the **level curves** where $p(x)$ is constant, hence where the Mahalanobis distance is constant.

***Special Case***: The variance matrix $\Sigma$ is **diagonal**:
![[Pasted image 20220809153537 - Plot.png]]

***Special Case***: The variance matrix $\Sigma = \sigma^2 I$:
![[Pasted image 20220809153623 - Plot.png]]

---
# Original Files
![[Pasted image 20220809145008.png]]
![[Pasted image 20220809145029.png]]
![[Pasted image 20220809152720.png]]
![[Pasted image 20220809152817.png]]
![[Pasted image 20220809153050.png]]
![[Pasted image 20220809153537.png]]
![[Pasted image 20220809153623.png]]
