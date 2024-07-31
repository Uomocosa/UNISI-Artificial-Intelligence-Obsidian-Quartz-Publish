###### Fast Recap:
- Main Supervised Learning Tasks:
	- **Function approximation**: $\underline{y} = \phi(\underline{x})$.
	- **Regression** (linear or non-linear) : $\underline{y} = \phi(\underline{x}) + \underline{\varepsilon}$, where $\underline{\varepsilon}$ is the *multivariate gaussian noise*.
	- **Pattern classification**: $\underline{y} = (g_1 (\underline{x}) ,\ \ldots ,\ g_c (\underline{x}))$.

- Universality of MLP:
	- *A non-linear MLP is very flexible*
	- According tho the theorem of *Universality of MLP*, an MLP with a hidden layer of sigmoid function an and a linear output is a **universal machine**.

- Mixture of Experts:
	- *A neural module can also be called an* **Expert**.
	- A neural module or **expert** realizes a function.
	- Then a **Gather** assigns **credit** to each expert (how much a neural module is reliable)

- Normal Uses of the Mixture of Experts:
	- **Divide et Conquer**: The feature region may be **partitioned** and each partition given to a different **expert**, usually when used this approach the gather will give a credit of $1$ to only one expert at a time (the one that knows about the current region) and all the the other credits will be equal to $0$.
	- **Overlapping regions**: Each expert will express a “likelihood” of being competent over any input $\underline{x}$, the *gather* will assign *credits* according to a pdf $\alpha_i = P(\omega_i \ | \ \underline{x})$ under the condition that $\sum \alpha_i = 1$ and $\underline{y} = \sum P(\omega_i \ | \ \underline{x}) \kern2px \varphi_i(\underline{x})$ imposed during both training and test.
	- **Training the whole Mixture of Experts**: Instead of training each *expert separately*, we can **train the whole model** including the *Gather*, which can learn automatically the values of all **credits** ($\alpha_i$).
	The Expert and the Gather are trained in parallel.

---
###### Recap:
***Main Supervised Learning Tasks***:
*A supervised MLP learns a transformation $\phi : \mathbb{R}^d \to \mathbb{R}^m$*
which in principle, may be applied to :
- **Function approximation**: $\underline{y} = \phi(\underline{x})$.
- **Regression** (linear or non-linear) : $\underline{y} = \phi(\underline{x}) + \underline{\varepsilon}$, where $\underline{\varepsilon}$ is the *multivariate gaussian noise*.
- **Pattern classification**: $\underline{y} = (g_1 (\underline{x}) ,\ \ldots ,\ g_c (\underline{x}))$.

***2-Class Classification***:
Depending on how we descrive the model, we might obtain a liner or non-linear classifier.
This is heavily influenced by the number of hidden layers in the MLP:
- If we have no hidden layers and a sigmoid activation function, the model will result into a **linear classifier**.
- While if we have at least 1 hidden layer (still considering sigmoid activation functions) the model will be **non-linear**


***Universality of MLP***:
*A non-linear MLP is very flexible*:

According tho the theorem of *Universality of MLP*, an MLP with a hidden layer of sigmoid function an and a linear output is a **universal machine**.

Given an unspecified number of neurons, and an unspecified method to learn the correct values of the weights, an MLP with just 1 hidden layer and sigmoid functions can generalize any function $\phi : \mathbb{R}^d \to \mathbb{R}^m$.

***Mixtures of Experts***:
*A neural module can also be called an* **Expert**.
A neural module or **expert** realizes a function.

Then a **Gather** assigns **credit** to each expert (how much a neural module is reliable), result in the final equation:
$$
\underline{y} = \sum_{i=1}^k \alpha_i \kern3px \varphi_i(\underline{x})
$$
Where:
- $\alpha_i \in [0 ,\ 1]$ is the **credit** assigned from the **Gather**

1. The feature region may be **partitioned** and each partition given to a different **expert**, usually when used this approach the gather will give a credit of $1$ to only one expert at a time (the one that knows about the current region) and all the the other credits will be equal to $0$.
2. **Overlapping regions**: Each expert will express a “likelihood” of being competent over any input $\underline{x}$, the *gather* will assign *credits* according to a pdf $\alpha_i = P(\omega_i \ | \ \underline{x})$ under the condition that $\sum \alpha_i = 1$ and $\underline{y} = \sum P(\omega_i \ | \ \underline{x}) \kern2px \varphi_i(\underline{x})$ imposed during both training and test.
3. Instead of training each *expert separately*, we can **train the whole model** including the *Gather*, which can learn automatically the values of all **credits** ($\alpha_i$)

---
# Original Files:
![[Pasted image 20220818105649.png]]
![[Pasted image 20220818110424.png]]
![[Pasted image 20220818110554.png]]
![[Pasted image 20220818110658.png]]
![[Pasted image 20220818110730.png]]

---
![[Pasted image 20220818110826.png]]
![[Pasted image 20220818110929.png]]
![[Pasted image 20220818111139.png]]
![[Pasted image 20220818111213.png]]

---
![[Pasted image 20220818111410.png]]
![[Pasted image 20220818111451.png]]
![[Pasted image 20220818111738.png]]