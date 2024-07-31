# All Slides of Artificial Intelligence
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

![[Pasted image 20220810172149.png]]
![[Pasted image 20220810172242.png]]
![[Pasted image 20220810172406.png]]
![[Pasted image 20220810172515.png]]

Where:
- $\nabla_{\underline{\Theta}} \kern3px l(\hat{\underline{{\Theta}}})$ is the **gradient** of the **log-likelihood function** $l(\hat{\underline{{\Theta}}})$ with respect to $\Theta$

![[Pasted image 20220810173046.png]]
![[Pasted image 20220810173143.png]]
![[Pasted image 20220810173239.png]]
![[Pasted image 20220810173302.png]]
![[Pasted image 20220810173321.png]]


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

![[Pasted image 20220812173824.png]]
![[Pasted image 20220812174105.png]]

![[Pasted image 20220817105453.png]]
![[Pasted image 20220817141336.png]]

---
![[Pasted image 20220817141459.png]]


![[Pasted image 20220817142146.png]]
![[Pasted image 20220817142717.png]]

---
![[Pasted image 20220817142806.png]]
![[Pasted image 20220817142826.png]]
![[Pasted image 20220817142952.png]]
![[Pasted image 20220817143123.png]]
![[Pasted image 20220817143149.png]]
![[Pasted image 20220817143219.png]]
![[Pasted image 20220817143239.png]]
![[Pasted image 20220817143428.png]]

---
![[Pasted image 20220817143729.png]]
![[Pasted image 20220817143754.png]]
![[Pasted image 20220817143820.png]]
![[Pasted image 20220817143841.png]]
![[Pasted image 20220817143851.png]]
![[Pasted image 20220817143900.png]]
![[Pasted image 20220817143910.png]]
![[Pasted image 20220817144318.png]]

![[Pasted image 20220817143910.png]]
![[Pasted image 20220817144318.png]]
![[Pasted image 20220817144519.png]]

---
![[Pasted image 20220817144623.png]]
![[Pasted image 20220817144725.png]]
![[Pasted image 20220817144933.png]]

![[Pasted image 20220817145129.png]]
![[Pasted image 20220817145329.png]]
![[Pasted image 20220817145917.png]]
![[Pasted image 20220817150028.png]]
![[Pasted image 20220817150126.png]]
![[Pasted image 20220817150201.png]]
![[Pasted image 20220817150339.png]]
![[Pasted image 20220817150353.png]]
![[Pasted image 20220817150401.png]]
![[Pasted image 20220817150412.png]]
![[Pasted image 20220817150450.png]]
![[Pasted image 20220817150420.png]]

![[Pasted image 20220818105649.png]]
![[Pasted image 20220818110424.png]]
![[Pasted image 20220818110554.png]]
![[Pasted image 20220818110658.png]]
![[Pasted image 20220818110730.png]]
![[Pasted image 20220818110424.png]]
![[Pasted image 20220818110554.png]]
![[Pasted image 20220818110658.png]]
![[Pasted image 20220818110730.png]]

---
![[Pasted image 20220818110826.png]]
![[Pasted image 20220818110929.png]]
![[Pasted image 20220818111139.png]]
![[Pasted image 20220818111213.png]]

---
![[Pasted image 20220818111410.png]]
![[Pasted image 20220818111451.png]]
![[Pasted image 20220818111738.png]]

![[Pasted image 20220819143150.png]]
![[Pasted image 20220819143320.png]]
![[Pasted image 20220819143357.png]]

> **NOTE**:
> We can use this to worsen the data to use in the training test, so to make a more robust model.

![[Pasted image 20220819144047.png]]

---
![[Pasted image 20220819145346.png]]
![[Pasted image 20220819145510.png]]
![[Pasted image 20220819145545.png]]
![[Pasted image 20220821183740.png]]

![[Pasted image 20220821183758.png]]
![[Pasted image 20220821183840.png]]

![[Pasted image 20220821184117.png]]
![[Pasted image 20220821184137.png]]
![[Pasted image 20220821193444.png]]
![[Pasted image 20220821193525.png]]

---
![[Pasted image 20220821193805.png]]
![[Pasted image 20220821193913.png]]
![[Pasted image 20220821194231.png]]
![[Pasted image 20220821194328.png]]
![[Pasted image 20220821194350.png]]

---
![[Pasted image 20220821194420.png]]
![[Pasted image 20220821194505.png]]
![[Pasted image 20220821194520.png]]
![[Pasted image 20220821194536.png]]

---
![[Pasted image 20220821194626.png]]
![[Pasted image 20220821194647.png]]

---
![[Pasted image 20220821194602.png]]
![[Pasted image 20220821194706.png]]
![[Pasted image 20220821194727.png]]
![[Pasted image 20220821194745.png]]

![[Pasted image 20220821194914.png]]
![[Pasted image 20220821194952.png]]
![[Pasted image 20220821195029.png]]
![[Pasted image 20220821195048.png]]
![[Pasted image 20220821195107.png]]

![[Pasted image 20220821195207.png]]
![[Pasted image 20220821195222.png]]
![[Pasted image 20220821195241.png]]
![[Pasted image 20220821195338.png]]
![[Pasted image 20220821195351.png]]
![[Pasted image 20220821195442.png]]

$h = 0.4$
![[Pasted image 20220821195517.png]]

$h = 0.2$
![[Pasted image 20220821195621.png]]

$h = 0.1$
![[Pasted image 20220821195642.png]]

![[Pasted image 20220821195716.png]]
![[Pasted image 20220821195731.png]]
![[Pasted image 20220821195753.png]]
![[Pasted image 20220821195815.png]]
![[Pasted image 20220821195827.png]]
![[Pasted image 20220821195837.png]]
![[Pasted image 20220821195854.png]]
![[Pasted image 20220821195916.png]]
![[Pasted image 20220821195931.png]]
![[Pasted image 20220821195948.png]]

---
![[Pasted image 20220821200003.png]]
![[Pasted image 20220821200021.png]]

---
![[Pasted image 20220821200032.png]]

***(Not to study):***
![[Pasted image 20220821200049.png]]

---
![[Pasted image 20220821200221.png]]
![[Pasted image 20220821200234.png]]
![[Pasted image 20220821200251.png]]
![[Pasted image 20220821200512.png]]
![[Pasted image 20220821200527.png]]
![[Pasted image 20220821200305.png]]
![[Pasted image 20220821200545.png]]

![[Pasted image 20220821200928.png]]
![[Pasted image 20220821201500.png]]
![[Pasted image 20220821201515.png]]
![[Pasted image 20220821201535.png]]
![[Pasted image 20220821201551.png]]
![[Pasted image 20220821201610.png]]
![[Pasted image 20220821201623.png]]
![[Pasted image 20220821201653.png]]
![[Pasted image 20220821201706.png]]
![[Pasted image 20220821201715.png]]
![[Pasted image 20220821201728.png]]
![[Pasted image 20220821201743.png]]

---
![[Pasted image 20220821201758.png]]
![[Pasted image 20220821201835.png]]
![[Pasted image 20220821201906.png]]
![[Pasted image 20220821201921.png]]
![[Pasted image 20220821201938.png]]
![[Pasted image 20220821202003.png]]

---
![[Pasted image 20220821202024.png]]
![[Pasted image 20220821202103.png]]

![[Pasted image 20220821202103.png]]
![[Pasted image 20220821202251.png]]
![[Pasted image 20220821202306.png]]
![[Pasted image 20220821202319.png]]
![[Pasted image 20220821202334.png]]
![[Pasted image 20220821202345.png]]
![[Pasted image 20220821202408.png]]
![[Pasted image 20220821202420.png]]
![[Pasted image 20220821202432.png]]
![[Pasted image 20220821202501.png]]
And so on, until we find a solution, usually it is not the optima one, to search for it we should search the whole tree.

![[Pasted image 20220821202623.png]]

---
![[Pasted image 20220821202655.png]]
![[Pasted image 20220821202806.png]]
![[Pasted image 20220821202824.png]]
![[Pasted image 20220821202846.png]]
![[Pasted image 20220821202858.png]]
![[Pasted image 20220821202925.png]]
![[Pasted image 20220821202938.png]]

---
![[Pasted image 20220821202955.png]]
![[Pasted image 20220821203012.png]]

---
![[Pasted image 20220821203024.png]]
![[Pasted image 20220821203035.png]]
![[Pasted image 20220821203051.png]]
![[Pasted image 20220821203104.png]]
![[Pasted image 20220821203120.png]]
![[Pasted image 20220821203130.png]]
![[Pasted image 20220821203141.png]]

---
![[Pasted image 20220821203158.png]]
![[Pasted image 20220821203216.png]]
![[Pasted image 20220821203224.png]]
![[Pasted image 20220821203242.png]]
![[Pasted image 20220821203347.png]]
![[Pasted image 20220821203401.png]]
![[Pasted image 20220821203514.png]]
![[Pasted image 20220821203459.png]]
![[Pasted image 20220821203614.png]]

![[Pasted image 20220821203729.png]]
![[Pasted image 20220821203757.png]]
![[Pasted image 20220821203818.png]]
![[Pasted image 20220821203832.png]]
![[Pasted image 20220821203900.png]]

---
![[Pasted image 20220821203922.png]]
![[Pasted image 20220821203953.png]]
![[Pasted image 20220821204006.png]]
![[Pasted image 20220821204028.png]]
![[Pasted image 20220821204059.png]]
![[Pasted image 20220821204125.png]]
