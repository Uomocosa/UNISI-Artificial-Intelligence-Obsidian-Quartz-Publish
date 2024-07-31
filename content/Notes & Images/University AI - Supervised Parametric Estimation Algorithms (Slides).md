###### Differences between Non-Parametric and Parametric Estimation
- ***Parametric Estimation***: we search for the **parameters** ($\underline{\Theta}$) that describe a **PDF** of an arbitrary form, so we can calculate $p(\underline{x} \ | \ \omega_i)$
- ***Non-Parametric Estimation***: no assumption on the form of the **PDF** are made, we calculate $P(\omega_i \ | \ \underline{x_0})$ given the sample data or we first calculate $p(\underline{x_0} \ | \ \omega_i)$, $P(\omega_i)$ and $p(\underline{x_0})$ and  and then use the Bayes theorem to find the **posterior probability** $P(\omega_i \ | \ \underline{x_0})$.

---
![[Pasted image 20220810172242.png]]
![[Pasted image 20220812172423.png]]

##### Algorithms for Supervised Parametric Estimation
![[Pasted image 20220812172711.png]]
![[Pasted image 20220812172909.png]]
