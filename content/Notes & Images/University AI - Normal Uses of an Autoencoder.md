## Normal Uses of an Autoencoder
1. Let $\mathbb{R}^d$ be the original feature space, $\tau = \{(\underline{x} ,\ \underline{\hat{y}}) \ | \ \underline{x} \in \mathbb{R}^d ,\ \underline{\hat{y}} \in \mathbb{R}^m\}$, so our goal is to train an ANN to realize the function $\phi : \mathbb{R}^d \to \mathbb{R}^m$.
2. From $\tau$ we define $\tau’$ the training set for our **Autoencoder**: $\tau = \{(\underline{x} ,\ \underline{x})\}$ and then train our Autoencoder.
3. We remove just the output layer from our Autoencoder and obtain a new function $\psi: \mathbb{R}^d \to \mathbb{R}^k$ such that $k \lt d$ , using this function on the input $\underline{x}$ we obtain a new set $\tau'' = \{(\underline{x} ,\ \underline{z}) \ | \ \underline{z} \in \mathbb{R}^{k}\}$
4. We train a new MLP via **backpropagation** on $\tau''' = \{(\underline{z} ,\ \underline{\hat{y}})\}$ and we obtain the function $\hat{\phi}: \mathbb{R}^k \to \mathbb{R}^m$ .
5. We mount the two MLP (Autoencoder and new MLP) on top of each other and obtain the function $\phi : \mathbb{R}^d \to \mathbb{R}^m$
6. We can tune the completed MLP via backpropagation on the original data set $\tau$, if necessary
7. We can iterate this process stacking even more Autoencoder at the beginning of the whole MLP

---
# Original Files
![[Pasted image 20220819143150.png]]
![[Pasted image 20220819143320.png]]
![[Pasted image 20220819143357.png]]
![[Pasted image 20220819144047.png]]
