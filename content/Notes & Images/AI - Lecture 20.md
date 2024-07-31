###### Fast Recap:

---
###### Recap:
***CNN (Competitive Neural Networks)***:
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
<br>

***Can we train a feed-forward neural network $\phi(\underline{x})$ in an unsupervised manner, to estimate a PDF $p(\underline{x})$ ?***
⇒ *Yes, we can, but it’s tricky*

We need to make the cost function:
$$
C(\tau ,\ W) = p(\tau \ | \ W)
$$
Where $p(\underline{x})$ is the output of our neural network.
This formula means that #TODO 

![[Pasted image 20220906184612.png]]


---
# Original Files:
![[Pasted image 20220821194914.png]]
![[Pasted image 20220821194952.png]]
![[Pasted image 20220821195029.png]]
![[Pasted image 20220821195048.png]]
![[Pasted image 20220821195107.png]]
