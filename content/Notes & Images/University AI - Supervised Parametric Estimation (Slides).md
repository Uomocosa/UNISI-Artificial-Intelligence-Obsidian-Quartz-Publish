![[Pasted image 20220810172149.png]]
![[Pasted image 20220810172242.png]]
![[Pasted image 20220810172406.png]]
![[Pasted image 20220810172515.png]]

Where:
- $\nabla_{\underline{\Theta}} \kern3px l(\hat{\underline{{\Theta}}})$ is the **gradient** of the **log-likelihood function** $l(\hat{\underline{{\Theta}}})$ with respect to $\Theta$


---
###### ~Ex.: Max-Likelihood Math Formulas
![[Pasted image 20220810173046.png]]
![[Pasted image 20220810173143.png]]
![[Pasted image 20220810173239.png]]

---
###### ~Ex.: Handwritten Character Recognition with Supervised Parametric Estimation
![[Pasted image 20220810173302.png]]
![[Pasted image 20220810173321.png]]


*Referring to the second* "***Note****"*: 
- $P(w_i \ | \ \underline{x})$ : **real** probability that $\underline{x}$, the data or variable we want to classify belongs to/is identified as the class $\omega_i$ (*~ex.:* in reality the percentage of male and female is $48\% \ / \ 52\%$).
- $\hat{P}(w_j \ | \ \underline{x})$ : $\hat{P}(w_i \ | \ \underline{x})$ : **estimated** probability of $P(w_i \ | \ \underline{x})$ (*~ex.:* we estimate that the the percentage of male and female is $50\% \ / \ 50\%$ , tho this is not actually true).
- $\sum_{j \neq i}\hat{P}(w_j \ | \ \underline{x})$ : **estimated** error probability for the class $i$ .

