## Can we train a feed-forward neural network $\phi(\underline{x})$ in an unsupervised manner, to estimate a PDF $p(\underline{x})$ ?
⇒ *Yes, we can, but it’s tricky*

Using an RBF 

We define the cost function:
$$
C(\tau ,\ W) = p(\tau \ | \ W)
$$
![[Pasted image 20220920191034.png]]

Where $p(\tau \ | \ W)$ is the **Likelihood**:
$$p(\tau \ | \ \underline{\Theta}) = \prod_{k=1}^{n} p(\underline{x_k} \ | \ \underline{\Theta})$$
Where $p(\underline{x_k} \ | \ W)$ is defined as:
$$
p(\underline{x} \ | \ \underline{\Theta}) = \sum_{j=1}^{c} P(\omega_j) \kern2px p(\underline{x} \ | \ \omega_j ,\ \underline{\Theta_j})
$$




This formula means that #TODO 

![[Pasted image 20220906184612.png]]


---
# Original Files
![[Pasted image 20220821195107.png]]
