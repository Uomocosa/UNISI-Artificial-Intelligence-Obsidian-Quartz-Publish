## SP (Simple Perceptron)
- ***Convention***: *The input layer is not counted, it acts as a placeholder, therefore the* **SP** *is a* **$1$-Layer ANN**
- ***Notation***: *"$w_{ij}$ denotes the* **weight** *of the connection between the $j$-th input unit and the $i$-th output unit*
- **Computed Function $f : \mathbb{R} \to \mathbb{R}$** : let $f$ be the **activation function**, then:
$$
y_i = f(a_i) = f\left(\sum_{j=1}^{d} w_{ij} \kern4px x_j \right)
$$
In particular if $f$ is **linear** then: $y_i = \sum_{j} w_{ij} \kern4px x_j = \underline{w_i}^t \underline{x}$ 
Which is called **Simple Linear Perceptron**.

---
# Original Files
![[Pasted image 20220817144933.png]]
