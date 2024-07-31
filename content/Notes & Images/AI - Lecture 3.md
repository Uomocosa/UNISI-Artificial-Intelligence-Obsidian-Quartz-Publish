###### Fast Recap:
- Bayes Theorem
- Decision Boundary or Decision Rule
- Bayes Decision Rule
- Bayes Decision Rule with Discriminant Functions
- Maximum Likelihood
- First X Principal Components

---
###### Recap:
***Bayes Theorem***: 
$$
\begin{align}
1. \kern20px & P(A ,\ B) = P(B ,\ A)
\\[5px]
2. \kern20px & P(A ,\ B)= P(A) \cdot P(B \ | \ A) \\
&  P(B ,\ A)= P(B) \cdot P(A \ | \ B)
\\[5px]
3. \kern20px & P(A \ | \ B) = \frac{P(A)}{P(B)}\kern3pxP(B \ | \ A)
\end{align}
$$
Where:
- $P(A \ | \ B)$ is the conditional probability (a **pdf**) of the event $A$ happening in case of being in the condition of $B$, for example: 
$A =$ *probability of picking a girl in a crowd*
$B =$ *being in a engineering university*
$P(A) = 0.51$ (we consider the more general case, in the world the percentage of female is $52\%$ and of males is $48\%$ )
$P(A \ | \ B) = 0.20$ (in an engineering course the percentage of females is around $20\%$)

<br>

***Decision Boundary*** or ***Decision Rule***:
Knowing the **pdf**s and **conditional pdf**s of different events, for example we can create those pdfs on the basis of data we have gathered, we define the decision rule as the major probability of all the events, given some information.
For example, we take data on the distribution of males and females at different ours in an apartments for a month, we create many different conditional pdfs given all the information, and then we define the decision boundary as follows:
![[Pasted image 20220810161045.png]]
- $x$ in this case is the *time* variable.
- $F$ and $M$ are the condition of being *female* or *male*.
- $\theta$ is the **decision boundary**.

> **NOTE**:
> $\theta$ is a function, this is a particular case of it being a constant.

---
# Original Files:
![[Pasted image 20220810160711.png]]
![[Pasted image 20220810160723.png]]
![[Pasted image 20220810160832.png]]

---
###### ~Ex.:
- $p(x \ | \ F)$ : Probability that $x$ (the person knocking on our door) is **female**.
- $p(x \ | \ M)$ : Probability that $x$ is **male**.
- $\theta$ : decision boundary. 
![[Pasted image 20220810161045.png]]
---

![[Pasted image 20220810161332.png]]
![[Pasted image 20220810161416.png]]
