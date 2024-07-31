###### Fast Recap:
---
###### Recap:
***Validation of Classifiers***:
Given our **labeled data** we divide it in **training set** $Y = Y_1 \cup Y_2 \cup \ldots \cup Y_c$ , **test set** $\tau = \tau_1 \cup \tau_2 \cup \ldots \cup \tau_c$ and **validation set** $V = V_1 \cup V_2 \cup \ldots \cup V_c$ , then:
1. We select a model $p(\underline{x} \ | \ \underline{\Theta})$ .
2. Using the **training set** $Y$ we estimate $\hat{\underline{\Theta}}$ .
3. After defining a cost function we calculate the **evaluated error** $\hat{P}(\underline{x} \ | \ \underline{\Theta})$ on the **validation set** $V$ .
4. If $\hat{P}(\underline{x} \ | \ \underline{\Theta})$ is not good, we restart from point ($1.$ or $2.$)
5. We do the final evaluation of the model error ($\hat{P}(\underline{x} \ | \ \underline{\Theta})$) using the **test set** $\tau$ .

<br>

***“Leave One Out” Method*** : 
*Used if the data sample is small and it is difficult/expensive to add data*
1. Let $Y = \{ y_1 ,\ y_2 ,\ \ldots ,\ y_n \}$
2. Loop for $i = 1 : n$
$\underline{x} = y_i ,\kern30px Y’ = Y \ \backslash \ \{ y_i \}$
Use $Y’$ to estimate $\hat{\underline{\Theta}}$
Compute and store $\hat{P}(\text{error} \ | \ \underline{x})$ using the model with **hyperparameters** $\hat{\underline{\Theta}}$
3. $\hat{P}(\text{error}) = \operatorname{E}[\hat{P}(\text{error} \ | \ \underline{x})] = \frac{1}{n}\sum_{i=1}^{n}\hat{P}(\text{error} \ | \ \underline{y_i})$

- The error is always evaluated in “new data”, data that is not in the **training set** and the model has not yet seen.
- At the end, all data is used both for training and testing, no data is “wasted”.
- It must be used on small data set, this method **scales bad**

<br>

***“Many-Fold Crossvalidation” Method***:
*Alternative to the normal $Y ,\ V ,\ \tau$ method, it is based on the idea of the* “***Leave One Out***” *method, but it scales much better*
1. Let $Y = \{ y_1 ,\ y_2 ,\ \ldots ,\ y_n \}$
2. Loop for $i = 1 : k$ $\kern30px$ where: $k \lt n$
Create a test set $\tau_i$ with a certain percentage of still unused data.
Use $Y’ = Y \ \backslash \ \tau_i$ to estimate $\hat{\underline{\Theta}}$ .
Compute and store $\hat{P}(\text{error} \ | \ \tau_i)$ calculated on $\tau_i$ and using the newly founds **hyperparameters** $\hat{\underline{\Theta}}$ .
3. $\hat{P}(\text{error}) = \operatorname{E}[\hat{P}(\text{error} \ | \ \underline{x})] = \frac{1}{k}\sum_{i=1}^{k}\hat{P}(\text{error} \ | \ \tau_i)$

<br>

***Naming*** :
- $\mu ,\ \underline{\mu}$ : **mean** and **vector mean**
- $\sigma^2 ,\ \Sigma$ : **variance** and **covariance matrix**
- $\underline{\Theta}$ : **parameter vector**, for example: $\underline{\Theta} = (\underline{\mu} ,\ \Sigma)$
- $\omega_i$ : $i$ **classes**, for example the gender (male/female) we want to identificate.
- $w_i$ : *weight*
- $b_i$ : *bias*
- $\underline{x} ,\ \underline{y}$ : **data**, could mean data in input or training data.
- $Y = \{\underline{y_1} \ \ldots ,\ \underline{y_n}\}$ a set of data, it usually used to indicate the **training set**.
 We could find $Y = Y_1 \cup Y_2 \cup \ldots \cup Y_c$ where $Y_i$ refers to the data of a single class $\omega_i$ , and it is given according to the distribution $p(Y \ | \ \omega_i)$ .
- $\tau$ : set of data belonging to the **test set** .
- $V$ : set of data belonging to the **validation set**.
- $c$ : number of **samples** used as the **training set**
- $P(w_i \ | \ \underline{x})$ : **real** probability that $\underline{x}$, the data or variable we want to classify belongs to/is identified as the class $\omega_i$ (*~ex.:* in reality the percentage of male and female is $48\% \ / \ 52\%$).
- $\hat{P}(w_i \ | \ \underline{x})$ : **estimated** probability of $P(w_i \ | \ \underline{x})$ (*~ex.:* we estimate that the the percentage of male and female is $50\% \ / \ 50\%$ , tho this is not actually true).
- $g_i(\underline{x})$ : **discriminant function** of class $w_i$, usually it is defined as: 
$g_i(x) = \log p(\underline{x} \ | \ \omega_i) + \log P(\omega_i)$
$g_i(\underline{x}) = w_i^t \kern3px \underline{x} + b_i$ $\kern30px$(in the linear case)
-  $D(\underline{x}) = w_i$ : **decision rule**, a simple decision rule could be:
$D(\underline{x}) = \omega_i \kern15px \text{iff} \kern15px g_i(\underline{x}) \ge g_j(\underline{x})$

---
# Original Files:
![[Pasted image 20220812171801.png]]

*Referring to the second* "***Note****"*: 
- $P(w_i \ | \ \underline{x})$ : **real** probability that $\underline{x}$, the data or variable we want to classify belongs to/is identified as the class $\omega_i$ (*~ex.:* in reality the percentage of male and female is $48\% \ / \ 52\%$).
- $\hat{P}(w_j \ | \ \underline{x})$ : $\hat{P}(w_i \ | \ \underline{x})$ : **estimated** probability of $P(w_i \ | \ \underline{x})$ (*~ex.:* we estimate that the the percentage of male and female is $50\% \ / \ 50\%$ , tho this is not actually true).
- $\sum_{j \neq i}\hat{P}(w_j \ | \ \underline{x})$ : **estimated** error probability for the class $i$ .


![[Pasted image 20220812172423.png]]
![[Pasted image 20220812172711.png]]
![[Pasted image 20220812172909.png]]

---
![[Pasted image 20220812173204.png]]
![[Pasted image 20220812173235.png]]

The idea of projecting $\mathbb{X}$ on $\mathbb{Y}$ is the same as in the **Unscented Kalman Filter** and the **Particle Filter**, creating a **pdf** given some data:
![[Pasted image 20220812173519.png]]
![[Pasted image 20220812173543.png]]
