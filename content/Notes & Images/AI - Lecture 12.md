###### Fast Recap:

---
###### Recap:
***Multilayer Perceptron (MLP)***:
- **Fully Connected** layered architecture with **feed-forward** propagation of input signals.
- **Activation Functions** are usually **sigmoid** and/or **linear**
- **Dynamics**: simultaneous propagation of the signal with no delays, from the input layer to the output layer, traversing an arbitrary number of hidden layer (even $0$ hidden layers is acceptable)
- **Learning**: **supervised**, via the **gradient method** (**backpropagation**)

***Special Case: Simple Perceptron (SP)***:
- ***Convention***: *The input layer is not counted, it acts as a placeholder, therefore the* **SP** *is a* **$1$-Layer ANN**
- ***Notation***: *"$w_{ij}$ denotes the* **weight** *of the connection between the $j$-th input unit and the $i$-th output unit*
- **Computed Function $f : \mathbb{R} \to \mathbb{R}$** : let $f$ be the **activation function**, then:
$$
y_i = f(a_i) = f\left(\sum_{j=1}^{d} w_{ij} \kern4px x_j \right)
$$
In particular if $f$ is **linear** then: $y_i = \sum_{j} w_{ij} \kern4px x_j = \underline{w_i}^t \underline{x}$ 
Which is called **Simple Linear Perceptron**.

---
# Original Files:
![[Pasted image 20220817143729.png]]
![[Pasted image 20220817143910.png]]
![[Pasted image 20220817144318.png]]
![[Pasted image 20220817144519.png]]

---
![[Pasted image 20220817144623.png]]
![[Pasted image 20220817144725.png]]
![[Pasted image 20220817144933.png]]
