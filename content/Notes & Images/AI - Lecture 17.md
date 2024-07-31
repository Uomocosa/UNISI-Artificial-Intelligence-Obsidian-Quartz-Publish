###### Fast Recap:

---
###### Recap:
***May we use MLP as an estimate of the class-conditional PDFs?***
Since the output of an MLP can be seen as:
$$
y_i(\underline{x}) \simeq P(\omega_i \ | \ \underline{x}) = \frac{p(\underline{x} \ | \ \omega_i) \kern2px P(\omega_i)}{p(\underline{x})}
$$
We can write:
$$
\frac{y_i(\underline{x})}{P(\omega_i)} \simeq \frac{p(\underline{x} \ | \ \omega_i) }{p(\underline{x})}
$$
Which is knows as **scaled likelihood**.

- $p(\underline{x})$ is unknown, but can be estimated.
- Also $p(\underline{x})$ estimates are more robust than $p(\underline{x} \ | \ \omega_i)$ estimates, because we need to estimate only one estimate instead of $c$ other PDFs ($c$ : number of classes, $\omega_1 ,\ \ldots ,\ \omega_c$ ), also with the same logic if we estimate only $p(\underline{x})$ we will have $c$ times more data.
- Also if $P(\omega_i)$ changes over time (let’s say it assumes the new value $P'(\omega_i)$) , we can just reuse the same MLP, so no re-training necessary and use the following formula:
$$
\begin{align}
P'(\omega_i \ | \ \underline{x}) &=
\\[5px]
&= \kern10px \frac{p(\underline{x} \ | \ \omega_i) }{p(\underline{x})}P'(\omega_i) 
\\[5px]
&\simeq
\frac{y_i(\underline{x})}{P(\omega_i)} P'(\omega_i) 
\end{align}
$$

<br>

***RBF (Radial Basis Function) Networks***:
*A generalized linear discriminant*
![[Pasted image 20220908201154.png]]
- All weights between the input layer and the first hidden layer are equal to $1$.
- There could be a bias terms: $b_i$.
- The RB Function (Radial Basis Function), or **kernel** is defined as:
$$
\Large \varphi(\underline{x}) = e^{-\frac{\|\underline{x} - \underline{\mu_k}\|}{2\sigma_k^2}}
$$
- A simple RBF Network with just 1-hidden layer will have this form:
$$
y_i = \sum_{j=1}^{k} w_{ij}\kern3px \varphi(\underline{x}) + b_i
$$
- RB Functions realize a mixture of Gaussian PDFs, hence they are particularly suitable for pdf estimation.
- Like **MLP**s, RBF Networks are “universal” approximators.

For the learning part, it’s **supervised** 
$$
C(\tau ,\ w) = \frac{1}{2}\sum_i (\hat{y_i} - y_i)^2
$$
And we usually consider 2 approaches:
1. Via **gradient descent** over $C(w)$, we learn the parameters: $w_{ij}$, $b_i$, $\underline{\mu_k}$ and $\sigma_k$ .
2. $\underline{\mu_k}$ and $\sigma_k$ are **estimated statistically**, then the other parameters $w_{ij}$ and $b_i$ are estimated via linear algebra methods (such as *matrix inversion*), or via the precedent method *gradient descent*.

> **NOTE**:
> With RBF Networks we can apply **gradient-ASCENT** over **ML (Maximum Likelihood) method** in order to estimate PDFs.
>
> The **ML method** only works if the weights between the last hidden layer and the output layer sum up to $1$.
> 
> This can’t be done in **MLP**s because the constraint $\int p(x) \, dx = 1$ is violated, since they realize MLPs realize mixtures of activation functions that are not inherently pdfs.

---
# Original Files:
![[Pasted image 20220821183635.png]]
![[Pasted image 20220821183740.png]]
![[Pasted image 20220821183758.png]]
![[Pasted image 20220821183840.png]]
