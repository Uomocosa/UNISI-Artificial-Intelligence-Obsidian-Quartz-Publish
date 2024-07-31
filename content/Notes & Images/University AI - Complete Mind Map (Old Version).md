#### Turing Machine
###### Nastro
###### Alfabeto
###### Orologio
###### Testina
###### Stati Interni
###### Regole di Transizione

---
#### AI Discussion
###### The Imitation Game
###### Weak and Strong AI

---
#### Classification Problem
###### Event
###### Extract Features
###### Classify
###### Class

---
#### Types of Features
###### Numeric
###### Symbolic
###### Qualitative

---
#### Gaussian Distributions
###### Definition of Gaussian PDF, Multivariate Gaussian PDF, Mean and Variance
###### Mahalanobis distance
$$(\underline{x} - \underline{\mu})^T \kern4px \Sigma^{-1} \kern0px (\underline{x} - \underline{\mu})$$

---
#### Bayes Theorem
###### Decision Boundary or Decision Rule
###### Bayes Decision Rule
$$\underset{i \kern2px \in \kern2px \mathbb{N}}{\max} \ p(\underline{x} ,\ w_i) = p(\underline{x} \ | \ w_i) \cdot P(w_i)$$
###### Bayes Decision Rule with Discriminant Functions
###### Maximum Likelihood Decision
$$g_i(\underline{x}) = \log (\kern2px p(\underline{x} \ | \ w_i) )+ \log (\kern0px P(\omega_i))$$
###### Fist $X$ Principal Components


---
#### Likelihood
###### Likelihood of $\Theta$ given $Y$
$$
p(Y \ | \ \underline{\Theta}) = \prod_{k=1}^n p(y_k \ | \ \underline{\Theta})
$$
###### (ML) Maximum Likelihood Estimate
$$
\underline{\hat{\Theta}} : \underset{\underline{\hat{\Theta}}}{\max} \ p(Y \ | \ \underline{\hat{\Theta}})
$$
 If we want to find the ML Estimate we need to find $\underline{\hat{\Theta}}$ such that: $\nabla_{\underline{\hat{\Theta}}}\left\{p(Y \ | \ \underline{\hat{\Theta}})\right\} = 0$

###### Log-Likelihood
- Instead of the normal $p(Y \ | \ \underline{\Theta})$ we use $\log\left\{p(Y \ | \ \underline{\Theta})\right\}$
- If we want to find the ML Estimate we need to find $\underline{\hat{\Theta}}$ such that: $\nabla_{\underline{\hat{\Theta}}}\left\{\log\left\{p(Y \ | \ \underline{\hat{\Theta}})\right\}\right\} = 0$

###### Gaussian ML Estimate:
- If the PDF we want to estimate is Gaussian, then the ML Estimate is the Gaussian PDF having mean equal to the **sample mean** and variance equal to the **sample variance**.


---
#### Validation of Classifiers
###### Normal Method with 60/20/20 Training Validation Test Sets

###### “Leave One Out” Method
- *Used if the data sample is small and it is difficult/expensive to add data*
- For each single data, we iterate, the training set will be $n-1$ data, the validation set will be only $1$ piece of data, the error is computed averaging all the error on the validation sets.
- At each iteration $\hat{\underline{\Theta}}$ changes

###### “Many-Fold Crossvalidation” Method
- *Alternative to the normal $Y ,\ V ,\ \tau$ method, it is based on the idea of the* “***Leave One Out***” *method*.
- *Scales much better than the* “***Leave One Out***” *method*.
- Same as “***Leave One Out***” *method*, but instead of using $1$ piece of data for the Validation set we use $m$ data, where of course $m \lt n$.
- Like the LOO method, at each iteration $\hat{\underline{\Theta}}$ changes.
- Each new validation set of size $m$ (created at each iteration) has data never used before in previous validation set.

---
#### Supervised Learning
###### Non-Parametric Estimates

###### Relative Frequency Estimate
- If $k$ out of $n$ data are in $R$, we can estimate $P$ via the **relative frequency**:
$$
P \simeq \frac{k}{n}
$$

##### Easily Estimate a PDF:
*~Ex.:* we are searching for the pdf of males in a specific university, we use the region $R_n$ to estimate $p(\underline{x_0})$ from $n$ data.
- The estimate of $p(\underline{x_0})$ out of $n$ data is defined as: $p_n(\underline{x_0})$.

Then the estimate will be calculated from:
- $V_n$ be the volume of $R_n$ .
- $k_n$ be the number of data (out of $n$) in $R_n$ .

⇒ Then, $p_n(\underline{x_0})$ the estimate of $p(\underline{x_0})$ will be equal to:
$$p_n(\underline{x_0}) = \frac{k_n}{n \kern2px V_n}$$

###### Asymptotic Necessary and Sufficient Conditions
- We want to ensure $p_n(\underline{x_0}) \rightarrow p(\underline{x_0})$ , so:
1. $\lim_{n \rightarrow \infty} V_n = 0$
2. $\lim_{n \rightarrow \infty} k_n = \infty$
3. $\lim_{n \rightarrow \infty} \frac{k_n}{n} = 0$ (to guarantee convergence)

Solutions:
- **PARZEN WINDOW**: Fix the volume (*~Ex.:* $V_n = \frac{1}{\sqrt{n}}$) and determine $k_n$ consequently.
- **$k_n$-NEAREST NEIGHBOUR**: Fix $k_n$ (*~Ex.:* $k_n = \sqrt{n}$ ), and determine $V_n$ consequently, in such a way that exactly $k_n$ patterns fall in $R_n$ .

---
#### K-NN

#### Parzen Window

#### Kernels
- Before applying the **Parzen Window** or **K-NN** method, we apply a filter to the data using a kernel.

##### Hypercube Kernel
- The easiest kernel, it result into a steep separation of the data into inside and outside the region $R$
- The kernel formula is:
$$
\varphi(\underline{u}) = 
\left\{ \begin{array}{c}
\kern5px 1 & \kern5px |u_j| \le \frac{1}{2} \kern15px \forall \kern1px j = 1 ,\ 2 ,\ \ldots ,\ d
\\
\kern5px 0 &
\end{array}\right.
$$

##### Gaussian Kernel
- Most useful if the pdf to be estimated is Gaussian
$$
\varphi(\underline{u}) = \operatorname{N}(\underline{u}  \, ;\ \underline {0} \, ,\ 1)
$$

##### Dirac’s Kernel
$$
\delta_n(\underline{x}) = \frac{1}{V_n} \cdot \operatorname{\varphi} \left(\frac{\underline{x}}{h_n}\right)
$$
- Where $\varphi$ is the **hypercube kernel** function.
- $V_n = \left(h_n\right)^d$.
- If $h_n$ is **big** the function $\delta_n(\underline{x} - \underline{x_i})$ is a very smooth function.
- if $h_n$ is **really small**, $h_n \to 0$ , than $\delta_n(\underline{x} - \underline{x_i})$ is a **Dirac’s Delta** centered in $\underline{x_i}$.
- This was used as an useful example to understand how a different **kernel** can impact the quality of the estimate $p_n(\underline{x})$.


#### Estimated Probability
- Given a region $R$ with center in $x_0$ (which is the data we want to estimate)
- Let’s say we have $k$ (**labeled**) data points inside $R$.
- Let’s also say that we have $k_i$ data points in $R$ are labeled as belonging to class $\omega_i$
- Then the estimated probability $\hat{P}(\omega_i \ | \ \underline{x_0})$ is equal to:
$$
\hat{P}(\omega_i \ | \ \underline{x_0}) = \frac{k_i}{k}
$$

---
#### Nearest Neighbour Rule:
- $x_0$ the pattern to be classified will be classified with the nearest **labeled** data $x_i$.
- Let’s say $x_i$ belongs to class $\omega_i$, then we classify $x_0$ with class $\omega_i$
- It’s the same as doing a 1-NN classification

#### $k_n$-NN ($k_n$-Nearest Neighbour)
- Same as **K-NN** but instead of deciding on an arbitrary $K$ at the start, we decide on a $k_n$ which depends on the number of data $n$
- *~Ex.:*
$$
k_n = \alpha \cdot \sqrt{n}
$$
- Alpha is an hyperparameter that we can be decided arbitrarily, for example $\alpha = 1$.

---
#### ANN
##### Architecture
- **directed or un-directed graph**
- each node (or vertices) is called a *neuron* and each arch (or edge) is called a *synaptic connection*
- For each node we can define an *activation function*
- While for each arch we can define its *weight*.
- An architecture is completely defined with: *Vertices*, *Edges*, *Input Units*, *Output Units*, *Hidden Units*, *Weights* and *Activation Functions*.
- Typical Activation function: **Sigmoid function**: 
$$
f(a) = \frac{1}{1+ e^{-a}}, \kern15px f(a) \in [0 ,\ 1]
$$

###### Dynamics
- Defines “*How the signal propagates*”.
- Normal Dynamics are: 
The input data propagates from the input layer up to the output layer passing all hidden layer, every time a set of data propagates to a new layer, the arch that go into a single neuron are multiplied with their respective weights and the summed all together, lastly the activation function of the neuron is applied, this process repeat for each layer up to the output layer.


###### Training & Generalization
- The ANN learns from the examples contained in the **training set**.
- We can distinguish between a variety of learning types:
	- **Supervised**: all training data is labeled
	- **Unsupervised**: none of the training data is labeled
	- **Semi-Supervised**: some of the training data is labeled
	- **Reinforcement**: a reinforcement signal (either a **penalty** or a **reward**) is given every now and then.
- Learning it’s not enough if we do not generalize, that is, it’s necessary that the model will provide sufficient results when given **new data**.

---
#### MLP (Multilayer Perceptron)
 **Fully Connected** layered architecture with **feed-forward** propagation of input signals.
- **Activation Functions** are usually **sigmoid** and/or **linear**
- **Dynamics**: simultaneous propagation of the signal with no delays, from the input layer to the output layer, traversing an arbitrary number of hidden layer (even $0$ hidden layers is acceptable)
- **Learning**: **supervised**, via the **gradient method** (**backpropagation**)


#### SP (Simple Perceptron)
- 1-Layer ANN (no hidden layer, just input and output layer)

---
#### Different Learning Methods
##### Batch Mode:
$$
C(\tau, w) = C(W) = \frac{1}{2}\sum_{j=1}^{n}\sum_{i=1}^{m}(\hat{y_i} - y_i)^2
$$
- For each epoch the model sees all the data in the training set, then calculates the cost summing all the errors.

###### On-line Mode:
$$
C(W) = \frac{1}{2}\sum_{j=1}^{m}(\hat{y_i} - y_i)^2
$$
- For each epoch the cost function considers only one piece of data from the data set.
- Useful if we have a constant influx of new data and we want/need to update the model constantly, for example data taken from a website.

---
#### Delta Rule
- Once we have calculate the Cost $C(\tau ,\ w)$ during training, we need to update the weights.
- Using the gradient descent method:
$$
\begin{align}
& w' = w + \Delta w 
\\[5px]
& \text{where:} \kern15px \Delta w = -\eta \frac{\partial C}{\partial w}
\end{align}
$$
- Instead of calculating every time the derivative of $C$,we can apply the “**delta rule**”:
$$
\Delta w_{jk} = \eta \kern3px \delta_j \kern2px o_k
$$
Where:
$$
\large \delta_j = \left\{ \begin{array}{l} (\hat{y_j} - y_j)f'_j(a_j) & \text{if} \ j \in L_{\mathcal{l}} \\ \left(\sum_{i\in L_{k+1}} w_{ij} \kern4px \delta_i \right) \cdot f'_j(a_j) & \text{if} \ j \in L_{k} \kern15px \text{where:} \ k = \mathcal{l} -1 ,\ \ldots ,\ 0 \end{array} \right.
$$

---
#### Practical Insight for training ANN
##### Randomly initialize weights in a small 0-centered interval
##### Normalize the Inputs
##### Regularization: reduce the number of dimension of the data
##### Weight sharing: reduce the number of weights making two or more synapses use the same weights
##### Weight-Decay: Numerically smaller weights are usually better, add the sum of all weights to the cost function
##### Use more flexible activation function
##### Add a momentum or inertia term
$$\Delta w(t+1) = -\eta \frac{\partial C}{\partial \kern2px w(t)} + \rho \kern2px \Delta w(t)$$
Where: $\rho \in (0,\ 1)$ is the **momentum rate**, how much should we consider the old $\Delta w$ in the new one.

---
#### Main Supervised Learning Tasks 
*A supervised MLP learns a transformation $\phi : \mathbb{R}^d \to \mathbb{R}^m$*
- **Function approximation**: $\underline{y} = \phi(\underline{x})$.
- **Regression** (linear or non-linear) : $\underline{y} = \phi(\underline{x}) + \underline{\varepsilon}$, where $\underline{\varepsilon}$ is the *multivariate gaussian noise*.
- **Pattern classification**: $\underline{y} = (g_1 (\underline{x}) ,\ \ldots ,\ g_c (\underline{x}))$.

#### ***Universality of MLP***:
- *A non-linear MLP is very flexible*
- According tho the theorem of *Universality of MLP*, an MLP with a hidden layer of sigmoid function an and a linear output is a **universal machine**.

#### Mixtures of Experts
- *A neural module can also be called an* **Expert**.
- A neural module or **expert** realizes a function.
- Then a **Gather** assigns **credit** to each expert (how much a neural module is reliable), result in the final equation:
$$
\underline{y} = \sum_{i=1}^k \alpha_i \kern3px \phi_i(\underline{x})
$$
Where: $\alpha_i \in [0 ,\ 1]$ is the **credit** assigned from the **Gather**

##### Divide et Conquer
- The feature region may be **partitioned** and each partition given to a different **expert**, usually when used this approach the gather will give a credit of $1$ to only one expert at a time (the one that knows about the current region) and all the the other credits will be equal to $0$.

###### Overlapping regions
- Each expert will express a “likelihood” of being competent over any input $\underline{x}$, the *gather* will assign *credits* according to a pdf $\alpha_i = P(\omega_i \ | \ \underline{x})$ under the condition that $\sum \alpha_i = 1$ and $\underline{y} = \sum P(\omega_i \ | \ \underline{x}) \kern2px \varphi_i(\underline{x})$ imposed during both training and test.


###### Training the whole Mixture of Experts
- Instead of training each *expert separately*, we can **train the whole model** including the *Gather*, which can learn automatically the values of all **credits** ($\alpha_i$)
- The Expert and the Gather are trained in parallel.

---
#### Autoencoder
An ANN where the training data is defined as $\tau = \{(x_i ,\ x_i)\}$
![[Pasted image 20220819143150 - Graph.png]]



###### Uses of an Autoencoder
1. Let $\mathbb{R}^d$ be the original feature space, $\tau = \{(\underline{x} ,\ \underline{\hat{y}}) \ | \ \underline{x} \in \mathbb{R}^d ,\ \underline{\hat{y}} \in \mathbb{R}^m\}$, so our goal is to train an ANN to realize the function $\phi : \mathbb{R}^d \to \mathbb{R}^m$.
2. From $\tau$ we define $\tau’$ the training set for our **autoencoder**: $\tau = \{(\underline{x} ,\ \underline{x})\}$ and then train our autoencoder.
3. We remove just the output layer from our autoencoder and obtain a new function $\psi: \mathbb{R}^d \to \mathbb{R}^k$ such that $k \lt d$ , using this function on the input $\underline{x}$ we obtain a new set $\tau'' = \{(\underline{x} ,\ \underline{z}) \ | \ \underline{z} \in \mathbb{R}^{k}\}$
4. We train a new MLP via **backpropagation** on $\tau''' = \{(\underline{z} ,\ \underline{\hat{y}})\}$ and we obtain the function $\hat{\phi}: \mathbb{R}^k \to \mathbb{R}^m$ .
5. We mount the two MLP (autoencoder and new MLP) on top of each other and obtain the function $\phi : \mathbb{R}^d \to \mathbb{R}^m$
6. We can tune the completed MLP via backpropagation on the original data set $\tau$, if necessary
7. We can iterate this process stacking even more autoencoder at the beginning of the whole MLP


---
#### Using an ANN as a Non-parametric Estimator
- We can use an **MLP** as a non-parametric estimator for pattern recognition in 2 ways:
1. Use **MLPs** as **discriminant function**: Train them via *backpropagation* on a set labeled with $0/1$ outputs.
2. Probabilistic interpretation of the **MLPs** outputs.

<br>

- Since the output of an MLP can be seen as:
$$
y_i(\underline{x}) \simeq P(\omega_i \ | \ \underline{x}) = \frac{p(\underline{x} \ | \ \omega_i) \kern2px P(\omega_i)}{p(\underline{x})}
$$
- We can write:
$$
\frac{y_i(\underline{x})}{P(\omega_i)} \simeq \frac{p(\underline{x} \ | \ \omega_i) }{p(\underline{x})}
$$
Which is knows as **scaled likelihood**.
-  $p(\underline{x})$ is unknown, but can be estimated.
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


#### Theorem: Lippmann, Richard
- If we reach the global minimum using $0/1$ targets and the right **MLP** architecture, we are guaranteed that the **MLP** obtained this way is the optimal **Bayesian Classifier**, as long as the class-posteriors are continuous.
- *In practice, using backpropagation on real world data we will never find the global minimum*.

---
***RBF (Radial Basis Function) Networks***:
*A generalized linear discriminant*
- All weights between the input layer and the first hidden layer are equal to $1$.
- The RB Function (Radial Basis Function), or **kernel** is defined as:
$$
\Large \varphi(\underline{x}) = e^{-\frac{\|\underline{x} - \underline{\mu_k}\|}{2\sigma_k^2}}
$$
- For the learning part, it’s **supervised**,
And we usually consider 2 approaches:
1. Via **gradient descent** over $C(w)$, we learn the parameters: $w_{ij}$, $b_i$, $\underline{\mu_k}$ and $\sigma_k$ .
2. $\underline{\mu_k}$ and $\sigma_k$ are **estimated statistically**, then the other parameters $w_{ij}$ and $b_i$ are estimated via linear algebra methods (such as *matrix inversion*), or via the precedent method *gradient descent*.
-  Like **MLP**s, RBF Networks are “universal” approximators.

> **NOTE**:
> With RBF Networks we can apply **gradient-ASCENT** over **ML (Maximum Likelihood) method** in order to estimate PDFs.
>
> The **ML method** only works if the weights between the last hidden layer and the output layer sum up to $1$.
> 
> This can’t be done in **MLP**s because the constraint $\int p(x) \, dx = 1$ is violated, since they realize MLPs realize mixtures of activation functions that are not inherently pdfs.

---
#### ML Estimate:
*~Ex.:* We say that the pdf we want to try is a linear combination of 5 Gaussian PDFs, then we will search $\underline{\hat{\Theta}} = \{(\underline{\mu_1},\ \sigma_1^2),\ \ldots ,\ (\underline{\mu_5},\ \sigma_5^2)\}$ such that our assumption will be as close as possible to the real pdf (we minimize the cost)
- We will have that $\underline{\hat{\Theta}}$ has to respect:
$$
\sum_{k=1}^{n}P(\omega_i \ | \ \underline{x_k} ,\ \underline{\hat{\Theta}}) \cdot
\nabla_{\underline{\hat{\Theta}_i}}\log\left\{p(\underline{x} \ | \ \omega_i ,\ \underline{\hat{\Theta}_i})\right\} = 0 \kern30px \forall i = 1 ,\ \ldots ,\ c
$$


---
#### GMM (Gaussian Mixture Model)
$$
p(\underline{x} \ | \ \underline{\Theta}) = \sum_{j=1}^{c} P(\omega_j) \kern2px \operatorname{N}(\underline{\mu_j} ,\ \Sigma_j)
$$
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

---
##### k-Means Clustering Algorithm
1. Fix initial arbitrary (*~ex.:* random) values: $\underline{\hat{\mu}_1}(0) ,\ \ldots ,\ \underline{\hat{\mu}_c}(0)$.
2. Assign each $\underline{x_k}$ (for $k = 1 ,\ \ldots ,\ n$) to its closest mean $\underline{\hat{\mu}_j}(t)$.
3. Re-calculate $\underline{\hat{\mu}_j}(t)$ for $j = 1 ,\ \ldots ,\ c$ applying the previous equation for updating $\underline{\hat{\mu}_j}(t)$ (arithmetic mean of the pattern $\underline{x_k}$ in **cluster** $\omega_i$).
4. If $\exists \kern4px j \in \{1 ,\ \ldots ,\ c\} : \underline{\hat{\mu}_j}(t) \neq \underline{\hat{\mu}_j}(t-1)$ then iterate from point *2.*, this mean: 
If during the last iteration at least one value of $\underline{\hat{\mu}_j}$ changed, repeat.

---
#### *The Problem of Data Description*
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

---
#### Similarity Measures
- Within Cluster Distance
- Between Cluster Distance
![[Pasted image 20220821194727 - Graphs.png]]
![[Pasted image 20220821194706 - Equations.png]]

<br>

---
#### Hierarchical Clustering
###### Divisive Clustering
- Top-Bottom: **Divisive Clustering** (we start with 1 big cluster and separate until we have at least $c$ or clusters)
##### Agglomerative Clustering
- Bottom-Up: **Agglomerative Clustering**, that we will see later (we start with no cluster and agglomerate data into new and previously created cluster until we at least have $c$ clusters)

<br>


#### Differences of K-NN Classifier and K-Mean Clustering:
1.  K-NN is a **Supervised** machine learning while K-means is an **Unsupervised** machine learning.
2.  K-NN is a **classification** or **regression** machine learning algorithm while K-means is a **clustering** machine learning algorithm.
3.  K-NN is a **lazy learner** while K-Means is an **eager learner**. An eager learner has a model fitting that means a training step but a lazy learner does not have a training phase.
4.  K-NN performs much better if all of the data have the same scale but this is not true for K-means.

<br>


##### Utility of Clustering Algorithms
1. Finding the geometric/probabilistic properties of the data: (*~ex.:* center of mass and variance)
2. Describe the data in a concise fashion
3. Partitioning the data into $c$ sub-samples (useful for *dived et conquer* algorithms)
4. Finding good initialization (the centroids) for complex models such as: **GMM**s with **Max Likelihood**, **RBF**s, $\ldots$
5. Discretization of continuous features (*~ex.:* We can use the centroids and the number of data in each cluster to create an histograms of the data).
6. Replacing original big data set with one single cluster of it, useful when working with complex algorithms like **K-NN** or **Parzen-Window**.

<br>

#### CNN (Competitive Neural Networks)
![[Pasted image 20220908220358.png]]
**ARCHITECTURE**: In the output layer, there are 2 more type of connections:
1. ***Lateral connection*** (each output neuron is connected to each other output)
2. ***Self-connections*** (each output neuron has a connection that goes from itself to itself)

The *lateral connections* are inhibitory (their weights are $\lt 0$)
While the *self-connections* are *excitatory* (their weights are $\gt 0$)

Also at the end of the network there is a **MAXNET** component that realizes a **winner takes all** strategy, only one of the output units (a cluster) wins over the others (the losers are set to $0$).

**DYNAMICS**: Simple dynamics, the input is passed to the network, the network spits out the outputs ($\hat{y}_i$ for $i = 1 ,\ \ldots$) then the MAXNET selects the winner and turn off all the other outputs.

**LEARNING**: **On-line learning** that relies on the following rule:
$$
\Delta w_{ij} = \eta \kern2px (x_j - w_{ij})
$$

> **NOTE**:
> This formula is “**theoretically grounded**”.
> Ergo “*It’s a good learning formula, we don’t need to search for another one*”

<br>

#### Density Estimation:
==**MEANING** of “*Density Estimation*” : Estimating PDFs from Unlabeled Data==
![[Pasted image 20220907163117.png]]


<br>

#### Drawbacks of Statistical Approaches
*Parametric vs. Non-parametric techniques*
![[Pasted image 20220907163252.png]]
![[Pasted image 20220907163304.png]]


<br>

#### Universal Approximator
![[Pasted image 20220907163544.png]]



<br>
***(PNN) Parzen Neural Network***:
![[Pasted image 20220907163758.png]]

##### Possible Problems
![[Pasted image 20220907163914.png]]
![[Pasted image 20220907163953.png]]
![[Pasted image 20220907164005.png]]
![[Pasted image 20220907164016.png]]


#TODO 

#### Symbolic AI: Problem Solving
![[Pasted image 20220907171721.png]]
![[Pasted image 20220907171744.png]]

#### Tree search
- Breadth-first search 
- Uniform-cost search 
- Depth-first search
- Depth-limited search
- Iterative Deepening search

##### Breadth-first search
![[Pasted image 20220907172310.png]]


##### Uniform-Cost Search
![[Pasted image 20220907172348.png]]

##### Depth-First Search
![[Pasted image 20220907195031.png]]


##### (DLS) Depth-Limited Search
![[Pasted image 20220907195436.png]]



##### Iterative Deepening search

##### Greedy best-first search
![[Pasted image 20220907202452.png]]
![[Pasted image 20220907202534.png]]


###### A\* Search
Same as Greed-First Search, but also consider the whole cost of the path (from root to node $n$)
![[Pasted image 20220907202635.png]]
![[Pasted image 20220907203102.png]]
![[Pasted image 20220907203532.png]]

##### Admissible Heuristic (Definition & Theorem)
![[Pasted image 20220907203139.png]]


##### Optimality of A\* (proof)
![[Pasted image 20220907203509.png]]


---
##### *~Ex.: $n$-Queens*
![[Pasted image 20220907203646.png]]
![[Pasted image 20220907203729.png]]


#### Hill-Climbing Search
![[Pasted image 20220907203900.png]]
![[Pasted image 20220907203915.png]]


---
#### Simulated Annealing Search:
![[Pasted image 20220907220514.png]]

*Algorithm*:
![[Pasted image 20220907220547.png]]

**THEOREM***:
![[Pasted image 20220907220607.png]]


---
#### Local Beam Search
![[Pasted image 20220907220741.png]]


---
#### Genetic Algorithms
![[Pasted image 20220907220812.png]]


---
