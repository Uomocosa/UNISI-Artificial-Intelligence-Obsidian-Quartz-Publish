***Practical Issues and Some Insights***:
1. Weights must be initialized **randomly** and they must belong in a small interval $[-\varepsilon ,\ +\varepsilon]$.
⇒ If $\varepsilon$ is to big, the sigmoid will **saturate**.
⇒ if the weights are all equals to each other then the model **will not “brake symmetry”** (the weight in each layer will be equal to each other, no matter the number of **epochs**).
2. It’s a good practice to **normalize** the inputs, a typical choice is in the range $[-1 ,\ +1]$.
3. Using sigmoid function will automatically normalize the outputs in the interval $[0 ,\ 1]$.
4. **Regularization**: Reduce the number of dimension of the model, to do this we can opt for two famous techniques:
⇒ **Weight-Sharing**: Some connection are forced to use the same weight, the learning for those weights ($\Delta w$) is computed by averaging the different values of the originals $\Delta w_{ij}$ 
⇒ **Weight-Decay**: Numerically smaller weights means simpler solutions:
$$
C = \frac{1}{2}\sum_i \left(\hat{y_i} - y_i\right)^2 + \frac{\alpha}{2}\sum_{i,\ j} \left(w_{ij}\right)^2
$$
Where: $\frac{\alpha}{2}\sum_{i,\ j} \left(w_{ij}\right)^2$ : is called the **regularization term**, (if the weights increase so does the cost $C$ ).
1. We can use more flexible activation function, they will require more time in the learning phase, but should bring a better, faster and smaller model.
For example, instead of the common sigmoid, we might opt for:
$$
\large f(a) = \frac{\lambda}{1+e^{-(a-b)/\theta}}
$$
1. Learning may be more stable by including a **momentum term**, (or **inertia**), in the delta rule:
$$
\Delta w(t+1) = -\eta \frac{\partial C}{\partial \kern2px w(t)} + \rho \kern2px \Delta w(t)
$$
Where: $\rho \in (0,\ 1)$ is the **momentum rate**, how much should we consider the old $\Delta w$ in the new one.

---
# Original Files
![[Pasted image 20220818105649.png]]
![[Pasted image 20220818110424.png]]
![[Pasted image 20220818110554.png]]
![[Pasted image 20220818110658.png]]
![[Pasted image 20220818110730.png]]


