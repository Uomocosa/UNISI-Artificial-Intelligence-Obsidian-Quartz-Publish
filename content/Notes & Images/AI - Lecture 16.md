###### Fast Recap:
- Autoencoder
	- An ANN where the training data is defined as $\tau = \{(x_i ,\ x_i)\}$

- Normal Use of an Autoencoder
	1. Let $\mathbb{R}^d$ be the original feature space, $\tau = \{(\underline{x} ,\ \underline{\hat{y}}) \ | \ \underline{x} \in \mathbb{R}^d ,\ \underline{\hat{y}} \in \mathbb{R}^m\}$, so our goal is to train an ANN to realize the function $\phi : \mathbb{R}^d \to \mathbb{R}^m$.
	2. From $\tau$ we define $\tau’$ the training set for our **autoencoder**: $\tau = \{(\underline{x} ,\ \underline{x})\}$ and then train our autoencoder.
	3. We remove just the output layer from our autoencoder and obtain a new function $\psi: \mathbb{R}^d \to \mathbb{R}^k$ such that $k \lt d$ , using this function on the input $\underline{x}$ we obtain a new set $\tau'' = \{(\underline{x} ,\ \underline{z}) \ | \ \underline{z} \in \mathbb{R}^{k}\}$
	4. We train a new MLP via **backpropagation** on $\tau''' = \{(\underline{z} ,\ \underline{\hat{y}})\}$ and we obtain the function $\hat{\phi}: \mathbb{R}^k \to \mathbb{R}^m$ .
	5. We mount the two MLP (autoencoder and new MLP) on top of each other and obtain the function $\phi : \mathbb{R}^d \to \mathbb{R}^m$
	6. We can tune the completed MLP via backpropagation on the original data set $\tau$, if necessary
	7. We can iterate this process stacking even more autoencoder at the beginning of the whole MLP

---
###### Recap:
***Autoencoder (Auto-associative Neural Net)***:
Train a neural network such that it has at least 1-hidden layer, with dimensions of the last hidden layer smaller than the dimension of the input layer, also it’s data set is a supervised set that has same input and output $Y = \{(\underline{x_1} ,\ \underline{x_1}) ,\ \ldots ,\ (\underline{x_n} ,\ \underline{x_n})\}$
![[Pasted image 20220819143150 - Graph.png]]

If we separate the output layer what we end up with is an encoder and a decoder for our input data.
- We can use just the encoder and attach it to the beginning of a new NN and use it to reduce the dimension of the input data.
- We can use just the encoder to reduce all our input data and then use the new input with faster training time (smaller dimensions)
- We can use the whole autoencoder as a noisy filter for our data, worsening the training data to obtain a more general model. 

Tho the **general approach** of what we want to do is:
1. Let $\mathbb{R}^d$ be the original feature space, $\tau = \{(\underline{x} ,\ \underline{\hat{y}}) \ | \ \underline{x} \in \mathbb{R}^d ,\ \underline{\hat{y}} \in \mathbb{R}^m\}$, so our goal is to train an ANN to realize the function $\phi : \mathbb{R}^d \to \mathbb{R}^m$.
2. From $\tau$ we define $\tau’$ the training set for our **autoencoder**: $\tau = \{(\underline{x} ,\ \underline{x})\}$ and then train our autoencoder.
3. We remove just the output layer from our autoencoder and obtain a new function $\psi: \mathbb{R}^d \to \mathbb{R}^k$ such that $k \lt d$ , using this function on the input $\underline{x}$ we obtain a new set $\tau'' = \{(\underline{x} ,\ \underline{z}) \ | \ \underline{z} \in \mathbb{R}^{k}\}$
4. We train a new MLP via **backpropagation** on $\tau''' = \{(\underline{z} ,\ \underline{\hat{y}})\}$ and we obtain the function $\hat{\phi}: \mathbb{R}^k \to \mathbb{R}^m$ .
5. We mount the two MLP (autoencoder and new MLP) on top of each other and obtain the function $\phi : \mathbb{R}^d \to \mathbb{R}^m$
6. We can tune the completed MLP via backpropagation on the original data set $\tau$, if necessary
7. We can iterate this process stacking even more autoencoder at the beginning of the whole MLP

<br>

***ANNs : Patter Recognition and Probability Estimation***:
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
<br>

***Theorem: Lippmann, Richard***:
If we reach the global minimum using $0/1$ targets and the right **MLP** architecture, we are guaranteed that the **MLP** obtained this way is the optimal **Bayesian Classifier**, as long as the class-posteriors are continuous.

*In practice, using backpropagation on real world data we will never find the global minimum*.



---
# Original Files:
![[Pasted image 20220819143150.png]]
![[Pasted image 20220819143320.png]]
![[Pasted image 20220819143357.png]]

> **NOTE**:
> We can use this to worsen the data to use in the training test, so to make a more robust model.

![[Pasted image 20220819144047.png]]

---
![[Pasted image 20220819145346.png]]
![[Pasted image 20220819145510.png]]
![[Pasted image 20220819145545.png]]
