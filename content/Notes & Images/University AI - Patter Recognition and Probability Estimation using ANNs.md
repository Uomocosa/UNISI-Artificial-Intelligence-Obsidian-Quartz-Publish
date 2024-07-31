## Patter Recognition and Probability Estimation using ANNs
We can use an **MLP** as a non-parametric estimator for pattern recognition in 2 ways:
1. Use **MLP**s as **discriminant function**: Train them via *backpropagation* on a set labeled with $0/1$ outputs.
2. Probabilistic interpretation of the **MLP**s outputs.

> **NOTE**:
> The **MLP** output may be interpreted as a probability if and only if it is constrained within the $[0,\ 1]$ range. This is guaranteed if sigmoid activation function are used.
> We also need to assert that the sum of all outputs equal to 1, this is done if we let:
> $\hat{P}(\omega_i \ | \ \underline{x}) = \Large \frac{y_i(\underline{x})}{\sum_{j=1}^{c}y_j(\underline{x})}$ 
> Where: $y_j(\underline{x})$ is the $j$-th ANN output over the current input $\underline{x}$.
>
> Or we can use the **SOFTMAX** normalization:
> $\hat{P}(\omega_i \ | \ \underline{x}) \simeq y_i(\underline{x}) = \Large \frac{e^{a_i}}{\sum_{j=1}^{c} e^{a_i}}$ 

---
# Original Files
![[Pasted image 20220819145346.png]]
![[Pasted image 20220819145510.png]]
![[Pasted image 20220819145545.png]]
