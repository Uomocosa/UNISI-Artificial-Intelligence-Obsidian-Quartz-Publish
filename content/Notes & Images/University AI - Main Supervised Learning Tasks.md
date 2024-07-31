## Main Supervised Learning Tasks
*A supervised MLP learns a transformation $\phi : \mathbb{R}^d \to \mathbb{R}^m$*
which in principle, may be applied to :
- **Function approximation**: $\underline{y} = \phi(\underline{x})$.
- **Regression** (linear or non-linear) : $\underline{y} = \phi(\underline{x}) + \underline{\varepsilon}$, where $\underline{\varepsilon}$ is the *multivariate Gaussian noise*.
- **Pattern classification**: $\underline{y} = (g_1 (\underline{x}) ,\ \ldots ,\ g_c (\underline{x}))$.
<br>
***2-Class Classification***:
Depending on how we descrive the model, we might obtain a linear or non-linear classifier.
This is heavily influenced by the number of hidden layers in the MLP:
- If we have no hidden layers and a sigmoid activation function, the model will result into a **linear classifier**.
- While if we have at least 1 hidden layer (still considering sigmoid activation functions) the model will be **non-linear**

---
# Original Files
![[Pasted image 20220818110826.png]]
![[Pasted image 20220818110929.png]]
![[Pasted image 20220818111139.png]]