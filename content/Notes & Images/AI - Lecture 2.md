###### Fast Recap:
- **Turing machine**:
	- **Nastro**
	- **Alfabeto**
	- **Orologio**
	- **Testina**
	- **Stati Interni**
	- **Regole di Transizione**

- AI discussion
	- The Imitation Game
	- Weak and Strong AI

- Classification problem
	1. Event
	2. Extract Features
	3. Classify
	4. Class

- Types of features:
	- **Numeric**
	- **Symbolic
	- ****Qualitative**

- Gaussian Distribution
	- Definition of Gaussian PDF
	- Multivariate Gaussian PDF
	- Mean & Variance
	- **Mahalanobis Distance**

---
###### Recap:
Una **Macchina di Turing** è composta da:
1. Un **nastro**
2. Un **alfabeto** di cui un solo carattere è universalmente definito, la cella vuota "***#***"
3. Un **orologio** (clock) a tempo discreto
4. Una **testina** per scrivere e leggere sul nastro
5. Un certo numero di **stati interni**
6. Un insieme di **regole di transizione**, per determinare dato uno stato e una lettura la prossima azione da percorrere, l'inseme delle azioni è sempre lo stesso: \{**read** or **write**\} nella cella a \{**destra**, **sinistra** o nella **cella attuale**\}

Una macchina è definita ***Turing Complete*** se è capace di eseguire qualsiasi programma gli viene passato, date le regole sopra riportate della macchina di Turing.

<br>

***The Imitation Game***: Un osservatore ***C***, deve riconoscere il sesso di ***A*** e ***B*** rispettivamente femmina e maschio cercano di ingannarlo.
***Turing Test***: Un osservatore ***C*** deve riconoscere se l'interlocutore ***A*** è un computer o un essere umano, un computer si dice che ha passato il "Test di Turing" se riesce ad ingannare con successo ***C***.

<br>

***Weak AI***: *Un intelligenza artificiale non sarà in grado di pensare*, ovvero di comprendere cosa gli è chiesto, rappresenterà solo una funzione matematica complessa che associa ad una domanda posta una risposta.
***Strong AI***: *Un intelligenza artificiale può pensare*, anche se una sola AI potrebbe non essere in grado, un'insieme di intelligenze artificiali parallele e distribuite in una macchina potrebbe essere in grado di pensare come un uomo.

<br>

***Classification Problems*** ⇒ Decision problem, alcune applicazioni: *Vending Machine*, *Speech Recognition*, *Lip Reading*, *Biometric Recognition* (such as fingertips and face recognition), *Image Recognition*
I problemi di classificazioni possono essere schematizzati nel seguente diagramma:
![[Pasted image 20220809144454 - Diagram.png]]
1. ***Event***: evento nel mondo reale, che viene rivelato dalla macchina
2. ***Perception*** (FEATURE EXTRACTION): attraverso dei sensori vengono prese le “feature” dell’evento.
3. ***Action*** (CLASSIFICATION PROCESS): il modello associa le feature in ingresso ad una classe in uscita, ad esempio passata in ingresso una foto il modello mi restituirà $0$ se si tratta di della foto di un cane o $1$ se si tratta della foto di un gatto.

<br>

***Types of Features***:
1. **Numeric** ~ ex.: *number of black pixels*, *frequency of sound*
2. **Symbolic** ~ ex.: *text*
3. **Qualitative** ~ ex.: *tall*, *short*, *big*, *small*, *red*, *blue*, …

> **NOTE**:
> *Symbolic* e *Qualitative* features possono essere trasformate in *Numeric features*.

<br>

***Gaussian or Normal Distributions***:
$$
p(x) = 
\frac{1}{\sigma\kern2px\sqrt{2\pi}} 
\operatorname{exp}\left\{
	-\frac{1}{2}\left(
		\frac{x - \mu}{\sigma}
	\right)^2
\right\}
$$
Where:
- $\mu$ : **mean** of the distribution
- $\sigma$ : **variance** of the distribution

<br>

***Multivariate Gaussian Distributions***:
$$
p(x) = 
\frac{1}{|\Sigma|^{1/2}\kern3px\left(2\pi\right)^{d/2}} 
\operatorname{exp}\left\{
	-\frac{1}{2} \kern1px
	\left(x - \mu\right)^T \kern4px
	\Sigma^{-1} \kern0px
	\left(x - \mu\right)
\right\}
$$
Where:
- $\mu$ : **vector mean**
- $\sigma$ : **variance matrix**

<br>

***Definition of Mean and Variance***:
$$
\begin{align}
& \operatorname{E}[x] =  \int_{-\infty}^{+\infty} x \kern3px p(x) \kern3px dx = \mu
\\
& \operatorname{Var}[x] \triangleq  \operatorname{E}[\left(x - \mu\right)^2] =  \int_{-\infty}^{+\infty} \left(x - \mu\right)^2 \kern3px p(x) \kern3px dx = \sigma
\end{align}
$$
***Definition of Vector Mean and Variance Matrix (Multivariate)***:
$$
\begin{align}
& \operatorname{E}[ \kern1px \underline{x} \kern1px ] = \underline{\mu}
\\
& \operatorname{E}[ \kern2px (\underline{x} - \underline{\mu})(\underline{x} - \underline{\mu})^T \kern4px ] = \Sigma 
\end{align}
$$

<br>

***Distribution of Gaussian Data***:
If we plot the **eigenvector** of the **variance matrix** $\Sigma$ in a cartesian plane we obtain:
![[Pasted image 20220809153050 - Plot.png]]
- The quantity $(\underline{x} - \underline{\mu})^T \kern4px \Sigma^{-1} \kern0px (\underline{x} - \underline{\mu})$ is known as **Mahalanobis distance** between $\underline{x}$ and $\underline{\mu}$ , the hyper-ellipsoid we see in the graph are the **level curves** where $p(x)$ is constant, hence where the Mahalanobis distance is constant.

***Special Case***: The variance matrix $\Sigma$ is **diagonal**:
![[Pasted image 20220809153537 - Plot.png]]

***Special Case***: The variance matrix $\Sigma = \sigma^2 I$:
![[Pasted image 20220809153623 - Plot.png]]

---
# Original Files:
![[Pasted image 20220809142419.png]]
![[Pasted image 20220809142441.png]]
![[Pasted image 20220809142502.png]]
![[Pasted image 20220809143256.png]]
![[Pasted image 20220809143430.png]]
![[Pasted image 20220809143519.png]]
![[Pasted image 20220809143620.png]]
![[Pasted image 20220809143738.png]]
![[Pasted image 20220809143803.png]]
![[Pasted image 20220809143831.png]]
![[Pasted image 20220809144137.png]]
![[Pasted image 20220809144152.png]]
![[Pasted image 20220809144255.png]]
![[Pasted image 20220809143851.png]]
![[Pasted image 20220809143945.png]]
![[Pasted image 20220809144005.png]]
![[Pasted image 20220809144036.png]]

---
![[Pasted image 20220809144400.png]]
![[Pasted image 20220809144412.png]]
![[Pasted image 20220809144454.png]]
![[Pasted image 20220809144542.png]]
![[Pasted image 20220809144613.png]]
![[Pasted image 20220809144711.png]]
![[Pasted image 20220809144730.png]]
![[Pasted image 20220809144806.png]]
![[Pasted image 20220809144906.png]]
![[Pasted image 20220809144927.png]]

---
![[Pasted image 20220809145008.png]]
![[Pasted image 20220809145029.png]]
![[Pasted image 20220809152720.png]]
![[Pasted image 20220809152817.png]]
![[Pasted image 20220809153050.png]]
![[Pasted image 20220809153537.png]]
![[Pasted image 20220809153623.png]]
