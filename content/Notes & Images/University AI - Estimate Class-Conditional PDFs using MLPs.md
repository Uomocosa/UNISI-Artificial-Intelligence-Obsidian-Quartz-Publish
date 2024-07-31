## May we use MLP as an estimate of the class-conditional PDFs?
Since the output of an MLP can be seen as:
$$
y_i(\underline{x}) \simeq P(\omega_i \ | \ \underline{x}) = \frac{p(\underline{x} \ | \ \omega_i) \kern2px P(\omega_i)}{p(\underline{x})}
$$
We can write:
$$
\frac{y_i(\underline{x})}{P(\omega_i)} \simeq \frac{p(\underline{x} \ | \ \omega_i) }{p(\underline{x})}
$$
Which is knows as **scaled likelihood**.

- $p(\underline{x})$ is unknown, but can be estimated.
- Also $p(\underline{x})$ estimates are more robust than $p(\underline{x} \ | \ \omega_i)$ estimates, because we need to estimate only one estimate instead of $c$ other PDFs ($c$ : number of classes, $\omega_1 ,\ \ldots ,\ \omega_c$ ), also with the same logic if we estimate only $p(\underline{x})$ we will have $c$ times more data.
- Also if $P(\omega_i)$ changes over time (let’s say it assumes the new value $P'(\omega_i)$) , we can just reuse the same MLP, so no re-training necessary and use the following formula:
$$
\begin{align}
P'(\omega_i \ | \ \underline{x}) &=
\\[5px]
&= \kern10px \frac{p(\underline{x} \ | \ \omega_i) }{p(\underline{x})}P'(\omega_i) 
\\[5px]
&\simeq
\frac{y_i(\underline{x})}{P(\omega_i)} P'(\omega_i) 
\end{align}
$$
---
![[Pasted image 20220821183635.png]]
![[Pasted image 20220821183740.png]]
