## Learning Methods for ANN
First we need to decide on a **cost function**, and how many training samples are seen for each **epoch**:
- We can decide on seeing **all training samples** before taking a step of backpropagation using the [[#Batch Criterion Function]]
- Or we can decide to take a step of backpropagation for each training sample, this is called [[#Online Criterion Function]]

For each **epoch** we need to apply the [[#Gradient Descent]] formula to each weight.
- This formula is just a reference, as it can be used just to calculate the $\Delta w$ of the output layer, the more general formula is the [[University AI - Delta Rule|Delta Rule]]

---
##### Batch Criterion Function
$$
C(\tau, w) = C(W) = \frac{1}{2}\sum_{j=1}^{n}\sum_{i=1}^{m}(\hat{y_i} - y_i)^2
$$
Where:
- $\tau = \{ (\underline{x_1} ,\ \underline{y_1}) ,\ \ldots ,\ (\underline{x_1} ,\ \underline{y_1})\}$ : is the training set (**supervised**)
- $w$ : weight
- $n$ : number of all the data in the training set
- $m$ : dimension of the output.
- $\hat{y_i}$ : predicted output given by the ANN.

---
##### Online Criterion Function
$$
C(W) = \frac{1}{2}\sum_{j=1}^{m}(\hat{y_i} - y_i)^2
$$
The difference with the **Batch Criterion** is that in the online mode only one output is considered to calculate the **Cost** $C(W)$, while in the batch for each cost we consider $m$ outputs (a batch).

---
##### Gradient Descent
$$
w' = w + \Delta w
$$
Where $\Delta w$ is calculated as:
$$
\Delta w = - \eta \frac{\partial C}{\partial w}
$$
Where:
- $w$ : weight
- $\eta$ : **learning rate** ($\in \mathbb{R}$) which is decided arbitrarily (can also be non-constant)
- $C$ : **Cost Function**

---
# Original Files
![[Pasted image 20220817145129.png]]
<br>
