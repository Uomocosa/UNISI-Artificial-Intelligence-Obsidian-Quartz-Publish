###### Fast Recap:

---
###### Recap:
Given the **unlabeled data** $\tau = \{\underline{x_1} ,\ \ldots ,\ \underline{x_n}\}$ **iid (independent and identically distributed)** according to an **unknown pdf** $p(\underline{x})$, we assume a **parametric model** $p(\underline{x} \ | \ \underline{\Theta})$ of $p(\underline{x})$ and we search for an estimate of $\underline{\Theta} = (\theta_1 ,\ \ldots ,\ \theta_p)$ that respect the nature of the data.

*~Ex.:* We say that the pdf we want to try is a linear combination of 5 Gaussian PDFs, then we will search $\underline{\Theta} = \{(\underline{\mu_1},\ \sigma_1^2),\ \ldots ,\ (\underline{\mu_5},\ \sigma_5^2)\}$ such that our assumption will be as close as possible to the real pdf (we minimize the cost)

Assume now that:
- The number of classes $c$ is known.
- $P(\omega_i)$ are all estimated.
- The forms of $p(\underline{x} \ | \ \omega_j ,\ \underline{\Theta_j})$ are all known.
- $p(\underline{x} \ | \ \underline{\Theta})$ is identifiable, that means that $\underline{\Theta}$ is unique for this pdf: $\underline{\Theta} \neq \hat{\underline{\Theta}} \Rightarrow \exists \kern2px \underline{x} \in \mathbb{X} : p(\underline{x} \ | \ \underline{\Theta}) \neq p(\underline{x} \ | \ \hat{\underline{\Theta}})$ 
- $\underline{\Theta_i}$ is **functionally independent** of $\underline{\Theta_i}$ , for $i \neq j$

Then:
#TODO 

<br>

***ML (Maximum Likelihood) Estimation***:
Assume:
$$
p(\underline{x} \ | \ \underline{\Theta}) = \sum_{j=1}^{c} P(\omega_j) \kern2px p(\underline{x} \ | \ \omega_j ,\ \underline{\Theta_j})
$$
We define the **Likelihood** as:
$$
p(\tau \ | \ \underline{\Theta}) = \prod_{k=1}^{n} p(\underline{x_k} \ | \ \underline{\Theta})
$$
Assuming that $p(\underline{x} \ | \ \underline{\Theta})$ is differentiable we have:
$$
\nabla_{\underline{\Theta_i}}\kern1px l = \sum_{k=1}^{n} \frac{1}{p(\underline{x_k} \ | \ \underline{\Theta})} \cdot \nabla_{\underline{\Theta_i}}\left\{\sum_{j=1}^{c} P(\omega_j) \kern2px p(\underline{x} \ | \ \omega_j ,\ \underline{\Theta_j})\right\}
$$
We need to have the following constraint, respected:
$$
\nabla_{\underline{\Theta_i}}\kern1px l = 0
$$
To do this $\underline{\hat{\Theta}} = \{\underline{\hat{\Theta}_1} ,\ \ldots ,\ \underline{\hat{\Theta}_c}\}$ needs to respect the following constraint:
$$
\sum_{k=1}^{n}P(\omega_i \ | \ \underline{x_k} ,\ \underline{\hat{\Theta}}) \cdot
\nabla_{\underline{\hat{\Theta}_i}}\log\left\{p(\underline{x} \ | \ \omega_i ,\ \underline{\hat{\Theta}_i})\right\} = 0 \kern30px \forall i = 1 ,\ \ldots ,\ c
$$
---
# Original Files:
![[Pasted image 20220821184040.png]]
![[Pasted image 20220821184117.png]]
![[Pasted image 20220821184137.png]]
![[Pasted image 20220821193444.png]]
![[Pasted image 20220821193525.png]]

---
![[Pasted image 20220821193805.png]]
![[Pasted image 20220821193913.png]]
