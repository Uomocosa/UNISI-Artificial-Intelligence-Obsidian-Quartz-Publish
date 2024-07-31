###### Fast Recap:

---
###### Recap:

***Density Estimation***:
==**MEANING** of “*Density Estimation*” : Estimating PDFs from Unlabeled Data==
Has long been a major issue in patter recognition and machine learning. It is relevant to:
![[Pasted image 20220907163117.png]]
The problem is **difficult** and **still open**
"*One cannot guarantee a good approximation using a limited number of observation*"

<br>

***Drawbacks of Statistical Approaches***:
*Parametric vs. Non-parametric techniques*
![[Pasted image 20220907163252.png]]
![[Pasted image 20220907163304.png]]

<br>

***ANN (Artificial Neural Networks) for Density Estimation***:
![[Pasted image 20220907163544.png]]

<br>

***(PNN) Parzen Neural Network***:
*Algorithm*:
![[Pasted image 20220907163758.png]]
![[Pasted image 20220907163914.png]]
(The solution listed as $1.X$ are all solution to the $1.$ problem)

![[Pasted image 20220907163953.png]]
![[Pasted image 20220907164005.png]]
![[Pasted image 20220907164016.png]]

Also in the PNN algorithm it is recommended to **normalize data** within a ***zero-centred meaningful range*** (meaningful range means not too little not to big, to be distinguished from the small zero-center range used in ANN with sigmoid activation function.
This is especially helpful to:
![[Pasted image 20220907164412.png]]

<br>
***If we know $X$ we can upgrade the PNN training algorithm***:
![[Pasted image 20220821195854.png]]

<br>
***Architecture Selection***:
![[Pasted image 20220907165230.png]]

#TODO WHAT?? 
![[Pasted image 20220907165212.png]]


<br>

***Use of PNNs for pattern classification***:
![[Pasted image 20220907165709.png]]
![[Pasted image 20220907165721.png]]
![[Pasted image 20220907165736.png]]
![[Pasted image 20220821195948.png]]

<br>

***Complexity***:
![[Pasted image 20220907165852.png]]

**TRAINING COMPLEXITY***:
![[Pasted image 20220907165911.png]]

**TEST COMPLEXITY**:
![[Pasted image 20220907170004.png]]

Comparison of training and testing complexity with **SVM**s ( #TODO ) and with **PW** (Parzen Window) and $k_n$-NN ($k_n$-Nearest Neighbour)
*training comparison*
![[Pasted image 20220907170213.png]]
*testing comparison*:
![[Pasted image 20220907170236.png]]
To sum it up:
![[Pasted image 20220907170306.png]]

<br>

***Modelling Capabilities***:
![[Pasted image 20220907170349.png]]

***Definition of “Interesting PDFs”***:
**nonpaltry pdf**:
![[Pasted image 20220907170415.png]]

***Theorem***:
![[Pasted image 20220907170502.png]]


<br>




---
# Original Files:
![[Pasted image 20220821195150.png]]
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
