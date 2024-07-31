## CNN (Competitive Neural Networks)
“*A Competitive Neural Network is the equivalent of clustering for the Neural Network family*”

The idea behind CNNs is that the output neurons must compete among themselves to become active

==CNN are used to classify a set of input patterns==

There are two kinds of CNN:
- **Competitive Only** Neural Network (only **ONE** output may be active at once)
- **Hebbian** Neural Network (**SEVERAL** output may be active at once)
<br>
We will see just the **Competitive Only** Neural Networks.
<br>
The competitive learning rule has three main points:
1. A set of neurons that are all the same, except for synaptic weight
2. Limit imposed on the strength of each neuron
3. A mechanism that permits the neuron to compete, implementing a **winner takes all** strategy
To do this we can connect the output neuron to each other and impose that these *lateral connections* must be ***inhibitory*** (their weights are $\lt 0$)

---
## CNN Definition:
*Please note the similarity with K-Means Clustering*

**STRUCTURE**:
- $d$ : inputs where $d$ is the dimension of our feature space ($\underline{x} \in \mathbb{R}^d$)
- $K$ : outputs, $K$ decided arbitrarily (*like K-Means Clustering*)
- No hidden layer (1-layer neural network)
- All output neurons must have the same activation function (usually linear)
- The output neurons have all *lateral connection* such that each output neuron is connected to each other output neuron, these *later connections* are ***inhibitory*** (their weights must be $\lt 0$)
- To limit the weights we impose the following rule:
$$
\sum_{i}^{d} w_{ki}^2 = 1 \kern30px \forall \kern1px k
$$

To understand the subscripts please note the following figure:
![[Pasted image 20220920175651.png]]
<br>
**DYNAMICS**:
- Feedforward neural network.
- $\underline{v_i} = \underline{x} \cdot \underline{w}$
- After $v_i$ are all calculated only the output with the maximum output is set on (**MAXNET**):
$$
y_i = 
\left\{\begin{array}{l}
1 \kern15px \text{if}  \ v_i \gt v_k \ \forall \kern1px k
\\
0 \kern15px \text{otherwise}
\end{array}\right.
$$
<br>

**LEARNING**:
==**ONLY THE WEIGHTS RELATIVE TO THE WINNER OUTPUT ARE CHANGED**==
Also the learning is **ONLINE**, each single sample passed to network makes the weight change.
Let’s say that $y_i$ is our only output with value $1$ (the winner) all the other outputs are inactive ($= 0$).
The change $\Delta w_{ki}$ is defined as:
$$
\Delta w_{ki} = \eta (x_i - w_{ki})
$$
And it’s applied to only the weights with subscript $i$ (the ones referring to the winner output), all the others weights remain unchanged

==*This Delta makes it that the weight become more similar to the inputs.*==

---
## ~CNN Example
Assuming our feature vectors are 3D:
Starting point:
- Yellow dots : training set
- Red Crosses : Weights of the NN
![[Pasted image 20220920174424.png]]
<br>
Iteration over time:
- The red crosses will move toward the center of the cluster
![[Pasted image 20220920174602.png]]
Really similar to K-Mean Clustering







---
## From the Slides:
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

Here we see an example of the learning of a **CNN**:
![[Pasted image 20220906190103.png]]
<br>

***Where does the learning formula of the CNN comes from ?***
![[Pasted image 20220906190526.png]]
- We need to define $n_i(t)$ as a function dependent on time, since being a **on-line learning** algorithm $n_i$ will change possibly at each iteration.
- In our case the vector $\underline{\mu_i}(t)$ is the vector of the weights $\underline{w}$ of the network.
- 

![[Pasted image 20220906190924.png]]
- So $n_i(t)$ will become equal to: $n_i(t) +1$
- $\sum_{j=1}^{n_i(t)} \underline{x_j}^{(i)}$ will become equal to: $\sum_{j=1}^{n_i(t)} \underline{x_j}^{(i)} + \underline{x_{n_i(t)+1}^{(i)}}$ 

![[Pasted image 20220906191043.png]]
- We can simplify in the second passage $\frac{n_i(t)}{n_i(t) +1} \to 1$ since $n_i(t) \gg 1$

![[Pasted image 20220906191536.png]]

---

![[Pasted image 20220821194914.png]]
![[Pasted image 20220821194952.png]]
![[Pasted image 20220821195029.png]]
![[Pasted image 20220821195048.png]]
