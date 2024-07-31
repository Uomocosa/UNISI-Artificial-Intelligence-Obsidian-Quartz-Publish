## Bayes Decision Rule
Bayes decision rules relies on the maximum of the joint-probability 
$$
p(\underline{x} ,\ w_i) = p(\underline{x} \ | \ w_i) \cdot P(w_i)
$$

---
## Bayes Decision Rule with Discriminant Functions:
$$
\begin{align}
& D(\underline{x}) = w_i \kern15px \text{iff} \kern15px g_i(\underline{x}) \ge g_j(\underline{x})
\\[2px]
& \rightarrow g_i(\underline{x}) = p(\underline{x} \ | \ \omega_i) \cdot P(\omega_i) 
\\[2px]
& \rightarrow g_i(\underline{x}) = \log (\kern2px p(\underline{x} \ | \ \omega_i) )+ \log (\kern0px P(\omega_i))
\end{align}
$$
We define the **Maximum Likelihood Decision** as:
$$
g_i(\underline{x}) = \log (\kern2px p(\underline{x} \ | \ w_i) )+ \log (\kern0px P(\omega_i))
$$
In case of *Gaussian assumptions*, the MLD will become:
$$
g_i(\underline{x}) = -\frac{1}{2} (\underline{x} - \underline{\mu_i})^T \kern3px \Sigma_i^{-1} \kern1px (\underline{x} - \underline{\mu_i}) -\frac{1}{2}  \log \left|\Sigma_i^{-1} \right| + \log \kern1px P(w_i)
$$
--- 
# Original Files
![[Pasted image 20220810162153.png]]
![[Pasted image 20220810162302.png]]
![[Pasted image 20220810162348.png]]
![[Pasted image 20220810162453.png]]
![[Pasted image 20220810162854.png]]

---
![[Pasted image 20220810162939.png]]
![[Pasted image 20220810163053.png]]
![[Pasted image 20220810163356.png]]
