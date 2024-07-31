## Mixture of Experts
“*A neural module can also be called an* **Expert**“.
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
# Original Files
![[Pasted image 20220818111410.png]]
![[Pasted image 20220818111451.png]]
![[Pasted image 20220818111738.png]]
