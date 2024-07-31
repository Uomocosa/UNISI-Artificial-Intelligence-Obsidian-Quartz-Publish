###### Fast Recap:
- Likelihood
- Likelihood of Conditional Probabilities 
“Likelihood of $p(Y \ | \ \underline{\Theta})$“
- ML (Maximum Likelihood) Estimate
- Log-Likelihood
- Gaussian ML Estimate
- Validation of Classifiers
	- Normal Method: 60/20/20
	- “Leave One Out” Method
	- “Many-Fold Crossvalidation” Method
- Supervised Learning
	- Non-Parametric Estimate
	- Relative Frequency Estimate
	- Easily Estimate a PDF

---
###### Recap:
***First 2 Principal Components***: Given a set of data we can create a **Multivariate Gaussian Distribution** from it, the first-X principal component are the first-X **eigenvalues** of the **covariance matrix** of the distribution.

<br>

***Bayes Decision Rule***:
Bayes decision rules relies on the maximum of the joint-probability $p(\underline{x} ,\ w_i) = p(\underline{x} \ | \ w_i) \cdot P(w_i)$ .

<br>

***Bayes Decision Rule with Discriminant Functions***
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

<br>

***~Ex.: Diagonal Covariance Matrix $\Sigma_i = \sigma^2 \kern1px I$*** :
$$ 
\begin{align}
& g_i(\underline{x}) = \frac{\underline{\mu_i}^t}{\sigma^2} \underline{x} - \frac{1}{2\sigma^2}\underline{\mu_i}^t \kern2px \underline{\mu_i} + \log \kern1px P(\omega_i)
\\[2px]
& \huge \cdot \normalsize  
\kern15px w_i = \frac{\underline{\mu_i}^t}{\sigma^2} 
\kern30px w_i : \text{$i$-esim weight}
\\[2px]
& \huge \cdot \normalsize  
\kern15px b_i = \frac{1}{2\sigma^2}\underline{\mu_i}^t \kern2px \underline{\mu_i} + \log \kern1px P(\omega_i) 
\kern30px b_i : \text{$i$-esim bias}
\\[2px]
& g_i(\underline{x}) = w_i^t \kern3px \underline{x} + b_i
\end{align}
$$
In this particular we have that the MLD (Maximum Likelihood Decision) is linear with respect to $\underline{x}$.

<br>

***Naming*** :
- $\omega_i$ : $i$ **classes**, for example the gender (male/female) we want to identificate.
- $w_i$ : weights
- $b_i$ : bias
- $\underline{x}$ : data, could mean data in input or training data.
- $D(\underline{x}) = w_i$ : **decision rule**.
- $P(w_i \ | \ \underline{x})$ : probability that given the data $\underline{x}$ the corresponding class will be $w_i$ .
- $g_i(\underline{x})$ : **discriminant function** of class $w_i$, the Bayes decision rule can be rewritten as:

---
# Original Files:
![[Pasted image 20220810161721.png]]
![[Pasted image 20220810161737.png]]

==***First 2 Principal Components***== : the first 2 eigen-vectors of the **covariance matrix** of the **Gaussian distribution** of the data.

![[Pasted image 20220810162015.png]]

---
![[Pasted image 20220810162153.png]]
![[Pasted image 20220810162302.png]]
![[Pasted image 20220810162348.png]]
![[Pasted image 20220810162453.png]]
![[Pasted image 20220810162854.png]]

---
![[Pasted image 20220810162939.png]]
![[Pasted image 20220810163053.png]]
![[Pasted image 20220810163356.png]]
