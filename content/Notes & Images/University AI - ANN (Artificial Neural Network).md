## Definition of an ANN (Artificial Neural Networks)
An **ANN** is completely specified once we define its:

***1. Architecture***: 
An ANN is a **directed or un-directed graph** where each node (or vertices) is called a *neuron* and each arch (or edge) is called a *synaptic connection*, it has three subset: the *input units*, the *output units* and the *hidden units*.
⇒ For each node we can define an *activation function*
⇒ While for each arch we can define its *weight*.
An architecture is completely defined with: *Vertices*, *Edges*, *Input Units*, *Output Units*, *Hidden Units*, *Weights* and *Activation Functions*.

***1.1. Typical Activation Functions***: 
⇒ Step function or **TLU** (Threshold Logic Units): $f(a) = \mathbb{1}(a), \kern15px f(a) \in [0 ,\ 1]$
⇒ **Linear Function**: $f(a) = a, \kern15px f(a) \in \mathbb{R}$
⇒ **Sigmoid function**: $f(a) = \frac{1}{1+ e^{-a}}, \kern15px f(a) \in [0 ,\ 1]$
⇒ **Hyperbolic tangent sigmoid**: $f(a) = \tanh(a), \kern15px f(a) \in [-1 ,\ 1]$
⇒ **Gaussian**: $f(a) = N(a ;\ \mu ,\ \sigma^2), \kern15px f(a) \in [0 ,\ 1]$
⇒ **ReLU** (Rectifier Linear Units): $f(a) = \max(0,\ a), \kern15px f(a) \in [0 ,\ +\infty]$
⇒ **Leaky ReLU**: $f(a) = \max(\lambda \kern1px a,\ a), \kern15px \text{where} \ \lambda \in [-0.1 ,\ 0.1]$

***2. Dynamics***: 
*How the signal propagates.*
The dynamics of an ANN represent how the input data goes from start to end (how it “propagates”), we need to define how the **weights** interact with the data after they are processed by the **activation function**.
*~Ex.:* Let’s take $d$ input data $(x_1 ,\ x_2 ,\ \ldots ,\ x_d)$ these data will not have any transformation in the input (even this part can be changed), then they will pass through a first hidden layer where for each node the activation function will be something like:
$$
\begin{align}
& a_j = \sum_{i=1}^d w_i \kern2px  o_i
\\
& z_j = \sigma \left( a_j \right)
\end{align}
$$
Where: 
$o_i$ : old layers (from $1$ to $d$) (in this case the input)
$z_j$ : node $j$ belonging to the new layer (in this case the hidden layer)
$\sigma$ : sigmoid function (our chosen activation function)

*~Ex.:*
![[Pasted image 20220817143820.png]]

This process is then repeated until the signal reaches the output layer.

Also the dynamics also define the **clock** (time trigger) of the ANN, which depends on its family of networks.

> **NOTE**:
> The ANN topology specifies the hardware architecture, the value of the weights it’s the software, while the **ANN dynamics** (the living machine) represents the *running process*.

***3. Learning***: 
The ANN learns from the examples contained in the **training set** $\tau = \{\underline{z_1} ,\ \underline{z_2} ,\ \ldots ,\ \underline{z_n}\}$ which is a continuous-valued data sample drawn from an *underlying multivariate pdf*.
Main learning setups:
⇒ **Supervised Learning**: $\kern15px \tau = \{(\underline{x_1} ,\ \underline{y_1}) ,\ \ldots ,\ (\underline{x_n} ,\ \underline{y_n})\}$
⇒ **Unsupervised Learning**: $\kern15px \tau = \{\underline{x_1} ,\ \ldots ,\ \underline{x_n}\}$
⇒ **Semi-Supervised Learning**: $\kern15px \tau = \{(\underline{x_1} ,\ \underline{y_1}) ,\ \ldots ,\ (\underline{x_n} ,\ \underline{y_n}) ,\ \underline{x_{n+1}} ,\ \ldots ,\ \underline{x_{n+m}} \}$ 
$n$ training data are supervised, they are a set of input $x_i$ and output $y_i$, while $m$ data are unsupervised, we know the input $x_j$ but not its output
⇒ **Reinforcement Learning**: $\kern15px \tau = \{\underline{x_1} ,\ \underline{x_2} ,\ \ldots ,\ (\underline{x_t} ,\ \underline{y_t}) ,\ \underline{x_{t+1}} ,\ \ldots\}$ 
Where a reinforcement signal $y_t$ either a **penalty** or a **reward** is given every now and then.

***3.1. Generalization***: 
Learning is a process of progressive modification of the **connection weights**, aimed at inferring the (universal) law underlying the data.
Far from being a mere memorization of the data, the laws learned this way are expected to **generalize new data**, previously unseen, this is called **generalization capability**.

---
# Original Files:
![[Pasted image 20220817142806.png]]
![[Pasted image 20220817142826.png]]
![[Pasted image 20220817142952.png]]
![[Pasted image 20220817143123.png]]
![[Pasted image 20220817143149.png]]
![[Pasted image 20220817143219.png]]
![[Pasted image 20220817143239.png]]
![[Pasted image 20220817143428.png]]

---
![[Pasted image 20220817143729.png]]
![[Pasted image 20220817143754.png]]

![[Pasted image 20220817143820.png]]
![[Pasted image 20220817143841.png]]
![[Pasted image 20220817143851.png]]
![[Pasted image 20220817143900.png]]
![[Pasted image 20220817143910.png]]
![[Pasted image 20220817144318.png]]
