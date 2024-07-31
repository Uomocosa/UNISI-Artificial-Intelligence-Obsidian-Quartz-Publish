## Non-Parametric Decision Rule
- Let $\{\underline{x_1} ,\ \underline{x_2} ,\ \ldots ,\ \underline{x_n}  \}$ be a **supervised sample**.
- Take a ball (of volume $V$) around $\underline{x_0}$, the ball will embrace $k$ **patterns**.
- Among these $k$ patterns, let $k_i$ be the number of patterns belonging to class $\omega_i$.

Then we will have that the estimated probability $p_n(\underline{x_0} ,\ \omega_i)$, the probability that $\underline{x_0}$ will belong to the class $\omega_i$ is:
$$
\Large p_n(\underline{x_0} ,\ \omega_i) = \frac{k_i}{n \kern1px V}
$$

Also, the estimated probability $\hat{P}(\omega_i \ | \ \underline{x_0})$ is given by:
$$
\Large
\hat{P}(\omega_i \ | \ \underline{x_0}) = 
\frac
	{p_n(\underline{x_0} ,\ \omega_i)}
	{\sum_{j=1}^{c} p_n(\underline{x_0} ,\ \omega_j)}  =
\frac
	{\frac
		{k_i}
		{n \kern1px V}
	}{\sum_{j=1}^{c} \frac
		{k_j}
		{n \kern1px V}
	} = 
\frac
	{k_i}
	{k}
$$
Where:
- $\sum_{j=1}^{c} p_n(\underline{x_0} ,\ \omega_j)$ : means the probability that $\underline{x_0}$ will belong to one of the classes $k_j$, so it is equal to $\frac{k}{n \kern1px V}$.


---
# Original Files:
![[Pasted image 20220817141459.png]]

