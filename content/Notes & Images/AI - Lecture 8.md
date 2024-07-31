###### Fast Recap:
- Estimated Probability
---
###### Recap:
*Probability $P$ that a generic pattern $\underline{x}$, drawn from pdf $p(\cdot)$, belongs to an arbitrary region $R$ of the feature space*:
$$
P = \int_R p(\underline{x}) \kern10px d\underline{x}
$$
If $k$ out of $n$ data are in $R$, we can estimate $P$ via the **relative frequency**:
$$
P \simeq \frac{k}{n}
$$
- *Practical Problem*: Consider that if the region isn’t really big enough and the pdf $p(\cdot)$ is constant the probability $P$ will tend to $0$.

<br>

As $n$ (our number of data) increases, so does our region: $R_1 ,\ R_2 ,\ \ldots ,\ R_n$ , where the subscript means the number of data in the region, such that $\underline{x_0}$ belong to each of them, $\underline{x_0} \in R_i \ \forall \kern1px i$, where $\underline{x_0}$ is our pattern of interest (*~Ex.:* we are searching for the pdf of males in a specific university, we use the region $R_n$ to estimate $p(\underline{x_0})$ from $n$ data.
- $V_n$ be the volume of $R_n$ .
- $k_n$ be the number of data (out of $n$) in $R_n$ .
- $p_n(\underline{x_0})$ be the $n$-th estimate of $p(\underline{x_0})$, *~Ex.:* $p_n(\underline{x_0}) = \frac{k_n}{n \kern2px V_n}$ .

***Asymptotic Necessary and Sufficient Conditions***: we want to ensure $p_n(\underline{x_0}) \rightarrow p(\underline{x_0})$ :
1. $\lim_{n \rightarrow \infty} V_n = 0$
2. $\lim_{n \rightarrow \infty} k_n = \infty$
3. $\lim_{n \rightarrow \infty} \frac{k_n}{n} = 0$ (to guarantee convergence)

⇒ To satisfy these conditions, we can do one of two things:
1. Fix a proper volume, say $V_n = \frac{1}{\sqrt{n}}$ and determine $\frac{k_n}{n}$ consequently. (***Parzen Window***).
2. Fix $k_n$ (*~Ex.:* $k_n = \sqrt{n}$ ), and determine $V_n$ consequently, in such a way that exactly $k_n$ patterns fall in $R_n$ ($k_n$-nearest neighbor).

---
# Original Files:
![[Pasted image 20220812173732.png]]
![[Pasted image 20220812173824.png]]
![[Pasted image 20220812174105.png]]
