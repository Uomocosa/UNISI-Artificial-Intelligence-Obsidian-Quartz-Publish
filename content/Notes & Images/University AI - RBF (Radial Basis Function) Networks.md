## RBF (Radial Basis Function) Networks
- *A generalized linear discriminant*
- *RBF NN are conceptually similar to K-Nearest Neighbour, a predicted value is likely to be about the same as other items that have close values to the predictor variables*
One difference with the K-NN is that, here we train a Neural Network, in the K-NN however we have to store each training sample, much more space is required in the K-NN method.
- [[#Definition of Radial Basis Function]]

![[Pasted image 20220908201154.png]]
- RBF Network are 2-layer NN (input layer, 1 hidden layer, output layer)
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
## Definition of Radial Basis Function
A RBF is so named because the radius distance is the argument to the function, in our case:
$$
\varphi(\underline{x}) = \exp\left\{-\frac{\|\underline{x} - \underline{\mu_k}\|}{2\sigma_k^2}\right\}
$$
![[Pasted image 20220920182559.png]]

The further a neuron is from the point being evaluated the less influence it has.

---
# [Original Video](https://www.youtube.com/watch?v=OUtTI99uRf4)


---
# Original Files
![[Pasted image 20220821183758.png]]
![[Pasted image 20220821183840.png]]

