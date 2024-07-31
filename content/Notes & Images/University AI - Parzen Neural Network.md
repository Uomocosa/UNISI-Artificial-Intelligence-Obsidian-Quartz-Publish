## (PNN) Parzen Neural Network
Starting from the training set $\tau = \{x_1 ,\ \ldots ,\ x_n\}$
We want to obtain the estimate of $p(x_0)$ , let’s call it $\hat{p}(x_0)$.
To do this we can use the following algorithm:
1. Define $h_1 \in \mathbb{R}$
2. Let $h_n = \frac{h_1}{\sqrt{n-1}}$
3. Let $V_n = h_n^d$
4. For $i=1 : n$
	1. Let $\tau_i = \tau \backslash \{x_i\}$
	2. Let $\large y_i = \frac{1}{n-1} \sum_{x \in \tau_i} \frac{1}{V_n}\varphi\left(\frac{x_i - x_0}{h_n}\right)$
5. Let $S = \{(x_i ,\ y_i) \ | \ i = 1 ,\ \ldots ,\ n\}$ a new training set
6. Train an **ANN** via backpropagation over $S$.
7. Let $\hat{p}{(x_0)}$ be the function computed by the ANN
8. Return $\hat{p}(x_0)$


> **NOTE**:
> $\large y_i = \frac{1}{n-1} \sum_{x \in \tau_i} \frac{1}{V_n}\varphi\left(\frac{x_i - x_0}{h_n}\right)$ is the pdf estimation obtained by the Parzen window

> **NOTE**:
> $\varphi(z)$ is defined as the **hypercube function**.

---
## Some Insights:
If we use ReLU 


---
## Upgrade of the PNN: Better Approximation of the Tail of the Distribution
- **PROBLEM**: Using the PNN the output $\hat{p}(x_0)$ will never reach $0$, this is theoretically correct, but in practice it will result in an error, it’s better to have a PNN that gives $0$ when the $\hat{p}(x_0)$ is really small (an approximation if you will).

To solve this problem, first we normalize the data (which is always a good practice):
1. Let’s choose a meaningful interval $X$ zero-centered, for example let’s take $X = [0,\ 1]$.
2. We make the data fit into this $X$ interval (by normalization).
3. We choose some values $x_i$ a **little outside** $X$
4. We add the couples $\{(x_i ,\ 0)\}$to the training set $S$ (the training set to train the ANN) 
This way we incentive the PNN to actually assume $0$ values in the output layer.


---
## Upgrade of the PNN: Cross-Validated Likelihood
Another upgrade is to separate the training set $\mathcal{T}$ in a **validation set** $\mathcal{V}$, and another, smaller training set $\mathcal{T}' = \{\mathcal{T}\} \backslash \{\mathcal{V}\}$
1. Declare $k \in \mathbb{N}$ (not too big)
2. Choose and extract $k$ samples from $\mathcal{T}'$, creating another training set $\mathcal{T}'_k$
3. Execute the PNN algorithm over $\mathcal{T}'_k$
4. Evaluate the **Likelihood** of the model (learned from $\mathcal{T}'_k$) over $\mathcal{V}$ (this likelihood is called **cross-validated likelihood**)
5. If the likelihood is increased significantantly repeat from step $3.$, otherwise return the output of the PNN algorithm.

> **NOTE**: 
> The **cross-validated likelihood** needs to be divided by $\int_X \phi (x) dx$ at each integration step to be comparable


---
## Upgrade of the PNN: Mixture of Experts
- Create $c$ PNNs one for each class $w_i$ for $i = 1 ,\ \ldots ,\ c$
- Train each PNN only on the data from its respective class
- The output of the $i$-th PNN $\phi_i(x_0)$ is the conditional probability $p(x_0 \ | \ w_i)$
- Now we can apply the **Bayes Decision Rule** to decide to which class $x_0$ belongs to:
$$
\max_i \kern10px P(w_i) \cdot p(x_0 \ | \ w_i)
$$

- We consider the PNNs just created a single **Expert**
- Another one will be:
![[Pasted image 20220920212307.png]]
So we have two Expert in parallel now.
- For the **Gather** we simply train it using backpropagation
![[Pasted image 20220920212451.png]]

---
## Computational Complexity
The PNN with respect to the PW takes a long time to train, while the PW requires no training, but once the training is done the PNN requires a miniscule amount of computational complexity to find the estimate, while the PW takes a lot.

- PNN training: $O(W\cdot T)$ 
- PNN estimation time: $O(W)$
- PW estimation time: $O(n\cdot T)$


---
## Nonpaltry PDF
![[Pasted image 20220907170415.png]]

To make it simple a nonpaltry PDF is a PDF that is continuous in $\mathbb{R}$ expect in a closed subset.

Then for a **nonpaltry PDF** we have a theorem that says that for $n \to \infty$ the PNN converges to the actual PDF. 

---
## From the Slides
---
*Algorithm*:
![[Pasted image 20220907163758.png]]
![[Pasted image 20220907163914.png]]
(The solution listed as $1.X$ are all solution to the $1.$ problem)

![[Pasted image 20220907163953.png]]
![[Pasted image 20220907164005.png]]
![[Pasted image 20220907164016.png]]

Also in the PNN algorithm it is recommended to **normalize data** within a ***zero-centred meaningful range*** (meaningful range means not too little not to big, to be distinguished from the small zero-center range used in ANN with sigmoid activation function.
This is especially helpful to:
![[Pasted image 20220907164412.png]]

---
## If we know $X$ we can upgrade the PNN training algorithm
![[Pasted image 20220821195854.png]]

---
## Architecture Selection
![[Pasted image 20220907165230.png]]

#TODO WHAT?? 
![[Pasted image 20220907165212.png]]

---


***Use of PNNs for pattern classification***:
![[Pasted image 20220907165709.png]]
![[Pasted image 20220907165721.png]]
![[Pasted image 20220907165736.png]]
![[Pasted image 20220821195948.png]]


***Complexity***:
![[Pasted image 20220907165852.png]]

**TRAINING COMPLEXITY***:
![[Pasted image 20220907165911.png]]

**TEST COMPLEXITY**:
![[Pasted image 20220907170004.png]]

Comparison of training and testing complexity with **SVM**s ( #TODO ) and with **PW** (Parzen Window) and $k_n$-NN ($k_n$-Nearest Neighbour)
*training comparison*
![[Pasted image 20220907170213.png]]
*testing comparison*:
![[Pasted image 20220907170236.png]]
To sum it up:
![[Pasted image 20220907170306.png]]

<br>

***Modelling Capabilities***:
![[Pasted image 20220907170349.png]]

***Definition of “Interesting PDFs”***:
**nonpaltry pdf**:
![[Pasted image 20220907170415.png]]

***Theorem***:
![[Pasted image 20220907170502.png]]

---
# Original Files:
![[Pasted image 20220821195150.png]]
![[Pasted image 20220821195207.png]]
![[Pasted image 20220821195222.png]]
![[Pasted image 20220821195241.png]]
![[Pasted image 20220821195338.png]]
![[Pasted image 20220821195351.png]]
![[Pasted image 20220821195442.png]]

$h = 0.4$
![[Pasted image 20220821195517.png]]

$h = 0.2$
![[Pasted image 20220821195621.png]]

$h = 0.1$
![[Pasted image 20220821195642.png]]

![[Pasted image 20220821195716.png]]
![[Pasted image 20220821195731.png]]
![[Pasted image 20220821195753.png]]
![[Pasted image 20220821195815.png]]
![[Pasted image 20220821195827.png]]
![[Pasted image 20220821195837.png]]
![[Pasted image 20220821195854.png]]
![[Pasted image 20220821195916.png]]
![[Pasted image 20220821195931.png]]
![[Pasted image 20220821195948.png]]

---
![[Pasted image 20220821200003.png]]
![[Pasted image 20220821200021.png]]

---
![[Pasted image 20220821200032.png]]

***(Not to study):***
![[Pasted image 20220821200049.png]]

---
![[Pasted image 20220821200221.png]]
![[Pasted image 20220821200234.png]]
![[Pasted image 20220821200251.png]]
![[Pasted image 20220821200512.png]]
![[Pasted image 20220821200527.png]]
![[Pasted image 20220821200305.png]]
![[Pasted image 20220821200545.png]]

