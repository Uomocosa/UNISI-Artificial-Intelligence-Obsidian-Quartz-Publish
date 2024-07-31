###### Fast Recap:

---
Recap:
***Mixture of Gaussian Components: $\underline{\Theta_i} = \underline{\mu_i}$***
A **GMM (Gaussian Mixture Model)** is a mixture density having form:
$$
p(\underline{x} \ | \ \underline{\Theta}) = \sum_{j=1}^{c} P(\omega_j) \kern2px \operatorname{N}(\underline{\mu_j} ,\ \Sigma_j)
$$
With the following *component densities*:
$$
p(\underline{x} \ | \ \omega_j ,\ \underline{\Theta_j}) = \frac{1}{(2\pi)^{\frac{d}{2}} \cdot |\Sigma_j|^{\frac{1}{2}}} \cdot \exp \left\{ 
-\frac{1}{2} (\underline{x}-\underline{\mu_j})^t \cdot \Sigma_j^{-1} \cdot (\underline{x}-\underline{\mu_j})
\right\}
$$
Whose gradient w.r.t. (whit respect to) parameters $\Theta_i$ is:
$$
\nabla_{\underline{\mu_j}} \log\left\{p(\underline{x} \ | \ \omega_j ,\ \mu_j)\right\} = \Sigma_j^{-1}\kern2px(\underline{x} - \underline{\mu_j})
$$
From the previous lecture we have seen that the condition to be respected is:
$$
\sum_{k=1}^{n}P(\omega_i \ | \ \underline{x_k} ,\ \underline{\hat{\Theta}}) \cdot
\nabla_{\underline{\hat{\Theta}_i}}\log\left\{p(\underline{x} \ | \ \omega_i ,\ \underline{\hat{\Theta}_i})\right\} = 0 \kern30px \forall i = 1 ,\ \ldots ,\ c
$$
So we will have that, since $\underline{\hat{\Theta}_j} = \underline{\hat{\mu}_j}$:
$$
\underline{\hat{\mu}_j} = 
\frac{
	\sum_{k=1}^{n} P(\omega_j \ | \ \underline{x_k} ,\ \hat{\underline{\mu}})
	\kern3px \underline{x_k}
}{
	\sum_{k=1}^{n} P(\omega_j \ | \ \underline{x_k} ,\ \hat{\underline{\mu}})}
$$
But there is a problem:
$$
\left\{\begin{array}{l}
\underline{\hat{\mu}_j} = \Large
\frac{
	\sum_{k=1}^{n} P(\omega_j \ | \ \underline{x_k} ,\ \hat{\underline{\mu}})
	\kern3px \underline{x_k}
}{
	\sum_{k=1}^{n} P(\omega_j \ | \ \underline{x_k} ,\ \hat{\underline{\mu}})
}
\\[5px]
\normalsize P(\omega_j \ | \ \underline{x_k} ,\ \hat{\underline{\mu}}) = \Large
\frac{
	p(\underline{x_k} \ | \ \omega_j ,\ \hat{\underline{\mu}})
	\kern3px P(\omega_j)
}{
	\sum_{i=1}^{c} p(\underline{x_k} \ | \ \omega_j ,\ \hat{\underline{\mu}}) \kern3px P(\omega_i)
}
\end{array}\right.
$$
The formulation is circular: to calculate $\underline{\hat{\mu}_j}$ we need to know $\underline{\hat{\mu}_j}$, we thus resort to the following **iterative algorithm**:
$$
\left\{\begin{array}{l}
\underline{\hat{\mu}}(0) = \text{inital "arbitrary" estimate}
\\[5px]
\underline{\hat{\mu}}(t+1) = \Large
\frac{
	\sum_{k=1}^{n} P(\omega_j \ | \ \underline{x_k} ,\ \hat{\underline{\mu}}(t))
	\kern3px \underline{x_k}
}{
	\sum_{k=1}^{n} P(\omega_j \ | \ \underline{x_k} ,\ \hat{\underline{\mu}}(t))
}
\end{array}\right.
$$
And we iterate for $t = 0$ up to $t = T$, where $T$ is decided arbitrarily.
![[Pasted image 20220821194350.png]]

<br>

***Unsupervised Non-Parametric Estimation: Clustering***
Update equation for $\underline{\hat{\mu}_j}(t+1)$:
![[Pasted image 20220821194420 - Equation (1).png]]

![[Pasted image 20220821194420 - Equation (2).png]]
The $P(\omega_i \ | \ \underline{x_k} ,\ \underline{\hat{\mu}}(t))$ formula just says that given:
- $c$ classes ($\omega_j$) each with a vector of parameters, in this case just the evaluated mean ($\underline{\hat{\mu}_j}(t)$)
The probability that $\underline{x_k}$ belong to class $\omega_j$ is $1$ if and only if the evaluated mean $\underline{\hat{\mu}_j}(t)$ is the closest to $\underline{x_k}$ according to the **Euclidean distance**, with respect to all other means ($\underline{\hat{\mu}_i}(t)$ for $i \neq j$)
⇒ So: $P(\omega_i \ | \ \underline{x_k} ,\ \underline{\hat{\mu}}(t))$ is just $1$ or $0$, this simplifies the calculation.
<br>

***k-Means Clustering Algorithm***:
1. Fix initial arbitrary (*~ex.:* random) values: $\underline{\hat{\mu}_1}(0) ,\ \ldots ,\ \underline{\hat{\mu}_c}(0)$.
2. Assign each $\underline{x_k}$ (for $k = 1 ,\ \ldots ,\ n$) to its closest mean $\underline{\hat{\mu}_j}(t)$.
3. Re-calculate $\underline{\hat{\mu}_j}(t)$ for $j = 1 ,\ \ldots ,\ c$ applying the previous equation for updating $\underline{\hat{\mu}_j}(t)$ (arithmetic mean of the pattern $\underline{x_k}$ in **cluster** $\omega_i$).
4. If $\exists \kern4px j \in \{1 ,\ \ldots ,\ c\} : \underline{\hat{\mu}_j}(t) \neq \underline{\hat{\mu}_j}(t-1)$ then iterate from point *2.*, this mean: 
If during the last iteration at least one value of $\underline{\hat{\mu}_j}$ changed, repeat.
<br>

***The Problem of Data Description***
$\underline{\hat{\mu}}$ and $\underline{\hat{\Sigma}}$ are **sufficient statistics** (they are a complete description of our data) if and only if, our data $\underline{x}$ is drawn from a **Gaussian Distribution**.

==Otherwise they would yield a wrong data description.==

To solve this problem we can use a **GMM** (Gaussian Mixture Model), and relying an an unbounded number of Gaussian Distribution we can describe any continuous and limited PDF.
This raises two problems:
1. Using an “unbounded” number of Gaussian PDFs brings complexity issues
2. Also if we mix too many Gaussian PDFs the problem overfits the 
training data and doesn’t generalize too well.

Alternatively we can use a **non-parametric technique** for estimating $p(\underline{x})$, for example the **Parzen-Window** or **$k_n$-Nearest Neighbors**, but we need to pay attention to the number of data used:
1. If $n = |\tau|$ is small (few data), then the estimate $p_n(\underline{x})$ is not reliable.
2. If $n = |\tau|$ is big, then $p_n(\underline{x})$ is over-complex, being memory-based, since $\tau$ must be kept in memory and involved in the calculations, this would not be a real data description.

⇒ ==Our best shot is to use **Clustering algorithms**.==
<br>

***Similarity Measures***
Instead of defining $k$ (the number of cluster) at the beginning we can define $d_0$ the maximum distance for which an element can be considered inside a **cluster**.
If in a single the “**within-cluster distance**” of 2 elements is further than $d_0$, then we create another cluster and re-separate the data.
<br>
***Hierarchical Clustering***:
The Hierarchical Clustering has 2 families:
1. Top-Bottom: **Divisive Clustering** (we start with 1 big cluster and separate until we have at least $c$ or clusters)
2. Bottom-Up: **Agglomerative Clustering**, that we will see later (we start with no cluster and agglomerate data into new and previously created cluster until we at least have $c$ clusters)
<br>

***Agglomerative Clustering algorithm:***
![[Pasted image 20220821194647 - Algorithm.png]]

Here is an example on how the algorithm works:
![[Pasted image 20220821194626.png]]
1. We start with creating a cluster with data $10$ and $13$ since they are the closest.
2. Then a new cluster with $7$ and $12$
3. We simultaneously agglomerate $14$ and $19$ into their own cluster, and add $4$ to the cluster containing $10$ and $13$
4. $\ldots$
<br>

***Between-Clusters Distance Measures***:
The most popular measures of distance between 2 clusters are:
![[Pasted image 20220821194727 - Graphs.png]]

The formula for obtaining these distances are reported here:
($X_i$ and $X_j$ are the two cluster we take into consideration)
![[Pasted image 20220821194706 - Equations.png]]
<br>

***Utility of Clustering Algorithms***:
1. Finding the geometric/probabilistic properties of the data: (*~ex.:* center of mass and variance)
2. Describe the data in a concise fashion
3. Partitioning the data into $c$ sub-samples (useful for *dived et conquer* algorithms)
4. Finding good initialization (the centroids) for complex models such as: **GMM**s with **Max Likelihood**, **RBF**s, $\ldots$
5. Discretization of continuous features (*~ex.:* We can use the centroids and the number of data in each cluster to create an histograms of the data).
6. Replacing original big data set with one single cluster of it, useful when working with complex algorithms like **K-NN** or **Parzen-Window**.

---
# Original Files:
![[Pasted image 20220821194033.png]]
![[Pasted image 20220821194231.png]]
![[Pasted image 20220821194303.png]]
![[Pasted image 20220821194328.png]]
![[Pasted image 20220821194350.png]]

---
![[Pasted image 20220821194420.png]]
![[Pasted image 20220821194505.png]]
![[Pasted image 20220821194520.png]]
![[Pasted image 20220821194536.png]]

---
![[Pasted image 20220821194602.png]]
![[Pasted image 20220821194626.png]]
![[Pasted image 20220821194647.png]]

---
![[Pasted image 20220821194706.png]]
![[Pasted image 20220821194727.png]]
![[Pasted image 20220821194745.png]]
