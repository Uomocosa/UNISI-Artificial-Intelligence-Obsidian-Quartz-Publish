## Delta Rule
***~Ex.: Online Mode, 1-Layer ANN***
*1-Layer ANN: 1 Input Layer, 1 Output Layer, we only have one set of weight.*
- $C(W) = \frac{1}{2}\sum_{j=1}^{m}(\hat{y_i} - y_i)^2$
- $y_i = f_i(a_i)$ $\kern30px$ $f_i$ : $i$-esim **activation function**
- $a_i = \sum_k w_{ik} \kern3px o_i$ $\kern30px$ $o_i$ : old layer, in this case the $i$-esim input.

After some calculation the result is:
$$
\Large \frac{\partial C}{\partial w} = \frac{\partial f(a_i)}{\partial a_i} o_i
$$

<br>

***~Ex.: Online Mode, 2-Layer ANN***
*Having an Hidden Layer adds to the computation $o_i$ in the last equation is not the input layer but in this case it’s the output of the hidden layer, so it depends on some weights and on an activation function*.
The $\Delta w$ of the output layer is:
$$
\Delta w = -\eta\frac{\partial C}{\partial w} = \eta \left(\sum_{i=1}^{m} w_{ij} \kern3px \delta_{i} \right) \cdot f'_{j}(a_j) \cdot o_k
$$
Where:
- $\large f_j’(a_j) = \frac{\partial}{\partial a_j}f_j(a_j)$
<br>
- $\large \delta_j = \left\{ \begin{array}{l} (\hat{y_j} - y_j)f'_j(a_j) & \text{if} \ j \in L_{\mathcal{l}} \\ \left(\sum_{i\in L_{k+1}} w_{ij} \kern4px \delta_i \right) \cdot f'_j(a_j) & \text{if} \ j \in L_{k} \kern15px \text{where:} \ k = \mathcal{l} -1 ,\ \ldots ,\ 0 \end{array} \right.$
<br>
- This is known as the **Generalized Delta Rule**: $\Delta w_{jk} = \eta \kern3px \delta_j \kern2px o_k$
- Learning is iterated for a defined number of consecutive cycles called **epochs**, using only the **training set**.
- An **epoch** is a cycle of application of the **delta-rule** over **all** the data in $\tau$.


---
# Original Files
![[Pasted image 20220817145129.png]]
![[Pasted image 20220817145329.png]]
![[Pasted image 20220817145917.png]]
![[Pasted image 20220817150028.png]]
![[Pasted image 20220817150126.png]]
![[Pasted image 20220817150201.png]]

---
###### ~Ex.:
![[Pasted image 20220817150339.png]]
![[Pasted image 20220817150353.png]]
![[Pasted image 20220817150401.png]]
![[Pasted image 20220817150412.png]]
![[Pasted image 20220817150450.png]]
![[Pasted image 20220817150420.png]]
