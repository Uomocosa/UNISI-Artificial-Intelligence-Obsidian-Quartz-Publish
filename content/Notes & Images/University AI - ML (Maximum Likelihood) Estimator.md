## Maximum Likelihood
Given $Y = \{\underline{y_1} \ \ldots ,\ \underline{y_n}\}$ a set of data that is given by the distribution $p(\underline{y} \ | \ \omega_i)$, given that they are all given by the same distribution we will say that they are **identically distributed**, suppose also that they **independent** between each other.
⇒ $y_i$ are **iid** (**independent** and **identically distributed**).

Due to the *independent* assumption we can say that:
$$
p(Y \ | \ \underline{\Theta}) = \prod_{k=1}^n p(y_k \ | \ \underline{\Theta})
$$
this is called the **likelihood of $\underline{\Theta}$ given $Y$**, this is a function of $\Theta$:
![[Pasted image 20220810172406 - Graph.png]]

We call the **Maximum Likelihood** (ML) **Estimate** $\underline{\hat{\Theta}}$ the one which maximizes $p(Y \ | \ \Theta)$.

<br>

***Log-Likelihood*** :
![[Pasted image 20220810172515.png]]
Where:
- $\nabla_{\underline{\Theta}} \kern3px l(\hat{\underline{{\Theta}}})$ is the **gradient** of the **log-likelihood function** $l(\hat{\underline{{\Theta}}})$ with respect to $\Theta$

<br>

***~Example*** : 
If we know that $p(Y \ | \ \Theta)$ is a **Gaussian Distribution** the maximum likelihood of the *mean* and *variance* are respectively the sample-mean and biased sample variance.

***Sample Mean*** : $\frac{1}{n} \sum^{n}_{k = 1} \underline{y_k}$ 
***Biased Sample Variance*** : $\frac{1}{n} \sum^{n}_{k = 1} (\underline{y_k} - \hat{\mu})^2$ 

(Bonus) **Unbiased Sample Variance*** : $\frac{1}{n-1} \sum^{n}_{k = 1} (\underline{y_k} - \hat{\mu})^2$ 

---
# Original Files:
![[Pasted image 20220810172138.png]]
![[Pasted image 20220810172149.png]]
![[Pasted image 20220810172242.png]]
![[Pasted image 20220810172406.png]]
![[Pasted image 20220810172515.png]]

Where:
- $\nabla_{\underline{\Theta}} \kern3px l(\hat{\underline{{\Theta}}})$ is the **gradient** of the **log-likelihood function** $l(\hat{\underline{{\Theta}}})$ with respect to $\Theta$

![[Pasted image 20220810173046.png]]
![[Pasted image 20220810173143.png]]
![[Pasted image 20220810173239.png]]
![[Pasted image 20220810173302.png]]
![[Pasted image 20220810173321.png]]

