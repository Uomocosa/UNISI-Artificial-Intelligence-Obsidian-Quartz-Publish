###### Fast Recap:

---
###### Recap:
***Likelihood*** :
Given $Y = \{\underline{y_1} \ \ldots ,\ \underline{y_n}\}$ a set of data that is given by the distribution $p(\underline{y} \ | \ \omega_i)$, given that they are all given by the same distribution we will say that they are **identically distributed**, suppose also that they **independent*** between each other.
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

<br>

***Naming*** :
- $\mu ,\ \underline{\mu}$ : **mean** and **vector mean**
- $\sigma^2 ,\ \Sigma$ : **variance** and **covariance matrix**
- $\underline{\Theta}$ : **parameter vector**, for example: $\underline{\Theta} = (\underline{\mu} ,\ \Sigma)$
- $\omega_i$ : $i$ **classes**, for example the gender (male/female) we want to identificate.
- $w_i$ : *weight*
- $b_i$ : *bias*
- $\underline{x} ,\ \underline{y}$ : **data**, could mean data in input or training data.
- $c$ : number of **samples** used as the **training set**
- $P(w_i \ | \ \underline{x})$ : probability that given the data $\underline{x}$ belongs to/is identified as the class $\omega_i$ .
- $g_i(\underline{x})$ : **discriminant function** of class $w_i$, usually it is defined as: 
$g_i(x) = \log p(\underline{x} \ | \ \omega_i) + \log P(\omega_i)$
$g_i(\underline{x}) = w_i^t \kern3px \underline{x} + b_i$ $\kern30px$(in the linear case)
-  $D(\underline{x}) = w_i$ : **decision rule**, a simple decision rule could be:
$D(\underline{x}) = \omega_i \kern15px \text{iff} \kern15px g_i(\underline{x}) \ge g_j(\underline{x})$


> **NOTE**:
> weights are named with $w$, while classes with $\omega$, it may cause confusion

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
