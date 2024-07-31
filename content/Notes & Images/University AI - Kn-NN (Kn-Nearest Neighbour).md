## $k_n$-Nearest Neighbour
Same as the **K-NN** algorithm but instead of choosing an arbitrary $K$, we make it a function of $n$.

*~Ex.:* $K = \sqrt{n}$

We instead need to choose a function, and it needs to respect these two necessary and sufficient conditions:
1. $\lim_{n \to \infty} k_n = \infty$ 
2. $\lim_{n \to \infty} \frac{k_n}{n} = 0$ 

For instance $K = \sqrt{n}$ satisfy both conditions.
We can also add an hyperparameter: $\alpha \in \mathbb{R}$, like $K = \alpha \cdot \sqrt{n}$ which will make the function more flexible.

The pdf estimation is as always:
$$
p_n(\underline{x_0}) = \frac{k_n}{n \kern2px V_n}
$$

---
## Professor Explanation:
Given that $h_n = \frac{\alpha}{\sqrt{n}}$ we could have some problems:
- If $\alpha$ is too small ⇒ $p_n(\cdot) = 0$ .
- If $\alpha$ is too big ⇒ $p_n(\cdot) = \operatorname{E}[ \kern3px p(\cdot) \kern1px ]$ .

We can solve this problem generalizing the value of $\alpha$, first we want to assert that:
1. $\lim_{n \to \infty} k_n = \infty$ 
1. $\lim_{n \to \infty} \frac{k_n}{n} = 0$ 

A possible solution to this problem is taking $k_n = \sqrt{n}$, such that:
$$
p_n(\underline{x_0}) = \frac{k_n}{n \ V_n} = \frac{1}{\sqrt{n} \ V_n}
$$
Now instead of deciding the Volume $V_n$ we create it this way:
1. Chose our center $\underline{x_0}$
2. Create an hypersphere of dimension $d$ around $\underline{x_0}$
3. Let the sphere expand until it includes $k_n = \sqrt{n}$ data.
4. Calculate the volume $V_n$ of this hypersphere.

To have more flexibility we can define $k_n = \alpha \cdot \sqrt{n}$ where $\alpha \in \mathbb{R}$ is an **hyperparameter** decided arbitrarily.
