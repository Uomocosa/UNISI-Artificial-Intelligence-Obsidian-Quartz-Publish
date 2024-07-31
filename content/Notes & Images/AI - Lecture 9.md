###### Fast Recap:

- K-NN (K-Nearest Neighbour)
	- Nearest Neighbour Rule
- Parzen Window
- Kernels
	- Hypercube Kernel
	- Gaussian Kernel
	- Dirac’s Kernel
- Kn-NN (Kn-Nearest Neighbour)
---
###### Recap:
- [Video](https://www.youtube.com/watch?v=UPXIdi_aTEg) to understand the differences of **K-NN**, **Parzen Window** Classifiers and what **Kernels** are.

***Differences of K-NN and Parzen Window Classifier***:
![[Pasted image 20220908171923.png]]
- **K-NN** (K-Nearest Neighbour) has fixed number of points and we calculate the size of the window 
*In the example both window of the 3-NN have 3 data points inside them, one region is larger the other is smaller*.
- **Parzen Window**: has a fixed window size and we count the number of data points inside the window.
*In the example both window of the Parzen Window have the same size, one has more data points inside them, the other has less*.

> **NOTE**:
> Both **Parzen Window** and **K-NN** are methods for a **PROBABILITY CLASSIFIER**.


***Kernel***:
As we can see from the next image, it’s unfair to classify based on a “step” function:
![[Pasted image 20220908173103.png]]
We classify this class (the yellow **X**) as 100% blue, because 2 blue dot are inside it and a red dot is just a little out of the region, so it’s presence is not considered during the classification.
⇒ To solve this problem we introduce the **KERNEL**s


Using the normal **K-NN** and **Parzen Window** Classifier we use a step function, saying that if you are inside the region $R$ “your vote” counts as $1$, as we can see in this other example:
![[Pasted image 20220908173357.png]]
In this example the class $X$ has a $66\%$ of being blue and $33\%$ of being red, not too fair.

Let’s see the difference if we use a **Kernel**:
![[Pasted image 20220908173553.png]]
This way the closer you are from the center, the more you count, the farther away you are the less you count, but you still count.

> **NOTE**:
> In practice the **Kernel** is a function.
> It usually takes in input the center of the Region and a data point, it gives out the “filtered” weight of that particular data point.

<br>

---
***Parzen Window***: 
Before training we can “filter” the data using a function, for example using the **hypercube function** that selects only the data in a specific region, an hypercube, wide $h_n$ , with $d$ dimensions (so its volume will be $V_n = (h_n)^d$ ).
We have defined the “***window function***” or “***kernel***” as:
$$
\varphi(\underline{u}) = 
\left\{ \begin{array}{c}
\kern5px 1 & \kern5px |u_j| \le \frac{1}{2} \kern15px \forall \kern1px j = 1 ,\ 2 ,\ \ldots ,\ d
\\
\kern5px 0 &
\end{array}\right.
$$
The **kernel** $\varphi\left( \frac{\underline{x_0}-\underline{x_i}}{h_n} \right)$ is a kernel having value $1$ only within the hypercube centered in $\underline{x_0}$ and having edge $h_n$, the **number of data** in this hypercube ($k_n$) is:
$$
k_n = \sum_{i=1}^{n} \ \varphi\left( \frac{\underline{x_0}-\underline{x_i}}{h_n} \right)
$$
As we have defined before the estimate $p_n(\underline{x_0})$ of the **unknown pdf $p(\cdot)$** is $\frac{k_n}{n \ V_n}$ , then:
$$
p_n(\underline{x_0}) = \frac{1}{n \kern2px V_n} \cdot \sum_{i=1}^{n} \ \varphi\left( \frac{\underline{x_0}-\underline{x_i}}{h_n} \right)

$$
> **NOTE**:
> We have defined $\varphi(\cdot)$ as the *hypercube function* but this form is equivalent for all **window functions**.

<br>


For example one common choice of a kernel is the **Gaussian Kernel**:
$$
\varphi(\underline{u}) = \operatorname{N}(\underline{u}  \, ;\ \underline {0} \, ,\ 1)
$$
- $\operatorname{N}(\cdot)$ : **Gaussian pdf**.
- $\underline{u}$ : vector of variables, this is a *multivariate gaussian distribution*
- $\underline{0}$ : mean
- $1$ : variance

<br>

***Sufficient Condition for Asserting that $p_n(\cdot)$ is a PDF*** :
1. $\varphi(\underline{u}) \ge 0 \kern15px \forall \kern2px \underline{u} \in \mathbb{R}^d$
2. $\int \varphi(\underline{u}) \ d\underline{u}  = 1$

> **NOTE**:
> Also, no matter the type of function $\varphi(\cdot)$, we can just take $h_n = \frac{\alpha}{\sqrt{n}}$ where $\alpha \in \mathbb{R}$ is an hyperparameter decided arbitrarily, and we can guarantee, as seen in the previous lecture, that the estimated pdf $p_n(\underline{x})$ will converge to the actual pdf $p(\underline{x})$, as the number of data $n \to \infty$ .

<br>

***Dirac’s Window Function***:
Let us define:
$$
\delta_n(\underline{x}) = \frac{1}{V_n} \cdot \operatorname{\varphi} \left(\frac{\underline{x}}{h_n}\right)
$$
Notice how:
- If $h_n$ is **big** the function $\delta_n(\underline{x} - \underline{x_i})$ is a very smooth function, having small variation and representing a rectangle centered in $\underline{x_i}$ high $\frac{1}{V_n}$ and total area equal to $1$.
- if $h_n$ is **really small**, $h_n \to 0$ , than $\delta_n(\underline{x} - \underline{x_i})$ is a **Dirac’s Delta** centered in $\underline{x_i}$.

> **NOTE**:
> This is a useful example to understand how a different **kernel** can impact the quality of the estimate $p_n(\underline{x})$.

<br>

***$k_n$-Nearest Neighbour*** :
Given that $h_n = \frac{\alpha}{\sqrt{n}}$ we could have some problems:
- If $\alpha$ is too small ⇒ $p_n(\cdot) = 0$ .
- If $\alpha$ is too big ⇒ $p_n(\cdot) = \operatorname{E}[ \kern3px p(\cdot) \kern1px ]$ .

We can solve this problem generalizing the value of $\alpha$, first we want to assert that:
1. $\lim_{n \to \infty} k_n = \infty$ 
1. $\lim_{n \to \infty} \frac{k_n}{n} = 0$ 

A possible solution to this problem is taking $k_n = \sqrt{n}$, such that:
$$
p_n(\underline{x_0}) = \frac{k_n}{n \ V_n} = \frac{1}{\sqrt{n} \ V_n}
$$
Now instead of deciding the Volume $V_n$ we create it this way:
1. Chose our center $\underline{x_0}$
2. Create an hypersphere of dimension $d$ around $\underline{x_0}$
3. Let the sphere expand until it includes $k_n = \sqrt{n}$ data.
4. Calculate the volume $V_n$ of this hypersphere.

To have more flexibility we can define $k_n = \alpha \cdot \sqrt{n}$ where $\alpha \in \mathbb{R}$ is an **hyperparameter** decided arbitrarily.

<br>

***Naming*** :
- $\mu ,\ \underline{\mu}$ : **mean** and **vector mean**
- $\sigma^2 ,\ \Sigma$ : **variance** and **covariance matrix**
- $\underline{\Theta}$ : **parameter vector**, for example: $\underline{\Theta} = (\underline{\mu} ,\ \Sigma)$
- $\omega_i$ : $i$ **classes**, for example the gender (male/female) we want to identificate.
- $w_i$ : *weight*
- $b_i$ : *bias*
- $\underline{x} ,\ \underline{y}$ : **data**, could mean data in input or training data.
- $\underline{x_0}$ : is our **pattern of interest**, for example an input data we want to estimate after training the model
- $p(\underline{x})$ : is the real probability we are searching.
- $p_n(\underline{x})$ : $n$-estimate of the *pdf* $p(\cdot)$ where $n$ is the *number of data* used to calculate this estimate.
- $Y = \{\underline{y_1} \ \ldots ,\ \underline{y_n}\}$ a set of data, it usually used to indicate the **training set**.
 We could find $Y = Y_1 \cup Y_2 \cup \ldots \cup Y_c$ where $Y_i$ refers to the data of a single class $\omega_i$ , and it is given according to the distribution $p(Y \ | \ \omega_i)$ .
- $\tau$ : set of data belonging to the **test set** .
- $V$ : set of data belonging to the **validation set**.
- $c$ : number of **samples** used as the **training set**
- $P(w_i \ | \ \underline{x})$ : **real** probability that $\underline{x}$, the data or variable we want to classify belongs to/is identified as the class $\omega_i$ (*~ex.:* in reality the percentage of male and female is $48\% \ / \ 52\%$).
- $\hat{P}(w_i \ | \ \underline{x})$ : **estimated** probability of $P(w_i \ | \ \underline{x})$ (*~ex.:* we estimate that the the percentage of male and female is $50\% \ / \ 50\%$ , tho this is not actually true).
- $g_i(\underline{x})$ : **discriminant function** of class $w_i$, usually it is defined as: 
$g_i(x) = \log p(\underline{x} \ | \ \omega_i) + \log P(\omega_i)$ 
$g_i(\underline{x}) = w_i^t \kern3px \underline{x} + b_i$ $\kern30px$(in the linear case) 
-  $D(\underline{x}) = w_i$ : **decision rule**, a simple decision rule could be:
$D(\underline{x}) = \omega_i \kern15px \text{iff} \kern15px g_i(\underline{x}) \ge g_j(\underline{x})$ 

---
# Original Files:
![[Pasted image 20220817102315.png]]

Where:
- $n$ : number of hypercubes.
- $R_n$ : hypercube (cube wide $h_n$ with dimension $d$).
- $V_n$ : Volume of the hypercube, $V_n= (h_n)^d$
- $\varphi(x)$: **window function**, or **kernel**
- $k_n$ : number of data given, in this case the sum of all the $n$ hypercubes' volumes.
- $p(\underline{x})$ : **multivariate pdf** where $\underline{x}$ is a vector.
- $p_n(\underline{x})$ : $n$-th estimation of the pdf $p(\underline{x})$.

![[Pasted image 20220817103629.png]]

> **NOTE**:
> **Gaussian Kernel** : $\varphi(\underline{u}) = \operatorname{N}(\underline{u} \ ; \ \underline{0} \ , \ 1)$
> $\underline{u}$ : vector of variables, this is a *multivariate gaussian distribution*
> $\underline{0}$ : mean
> $1$ : variance

![[Pasted image 20220817104105.png]]
![[Pasted image 20220817104547.png]]
Where: 
- $h_1$ : hyperparameter, width of the hypercubes.
- $n$ : hyperparameter, number of hypercubes we wish to take.

If we change the $p(x)$
![[Pasted image 20220817105223.png]]

----
![[Pasted image 20220817105313.png]]
![[Pasted image 20220817105453.png]]
