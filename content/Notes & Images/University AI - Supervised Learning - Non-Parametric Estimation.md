## Supervised Learning: Non-Parametric Estimation
Up until now we have always made assumption on the form of the **PDF** when estimating the probability $P(\omega_i \ | \ \underline{x})$.

To sum it up:
- Our objective is to estimate
$$
P(\omega_i \ | \ \underline{x}) = \frac{p(\underline{x} \ | \ \omega_i) \cdot P(\omega_i)}{p(\underline{x})}
$$
- We don’t want to make any kind of assumption on the underling PDF of the data.

We can opt for one of three options:
1. Estimate the pdf $p(\underline{x} \ | \ \omega_i)$ using the data we have available, then calculate $P(\omega_i \ | \ \underline{x})$ using the formula above.
2. Calculating directly $P(\omega_i \ | \ \underline{x})$ using the data, which is the result of a chosen discriminant function.
3. We first reduce the dimension space of the data, $\varphi : \mathbb{X} \to \mathbb{Y}$, then we estimate the probability using one of the other two methods ($1.$ or $2.$), but this time we make it using $\underline{y} = \varphi(\underline{x})$
Computing $P(\omega_i \ | \ \underline{y})$ turn out to be easier than computing $P(\omega_i \ | \ \underline{x})$


---
# Original Files
![[Pasted image 20220812173204.png]]
![[Pasted image 20220812173235.png]]

The idea of projecting $\mathbb{X}$ on $\mathbb{Y}$ is the same as in the **Unscented Kalman Filter** and the **Particle Filter**, creating a **pdf** given some data:
![[Pasted image 20220812173519.png]]
![[Pasted image 20220812173543.png]]
