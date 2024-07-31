## Autoencoders (Auto-associative Neural Net)
An ANN where the training data is defined as $\tau = \{(x_i ,\ x_i)\}$
<br>
Train a neural network such that it has at least 1-hidden layer, with dimensions of the last hidden layer smaller than the dimension of the input layer, also it’s data set is a supervised set that has same input and output $Y = \{(\underline{x_1} ,\ \underline{x_1}) ,\ \ldots ,\ (\underline{x_n} ,\ \underline{x_n})\}$
![[Pasted image 20220819143150 - Graph.png]]

If we separate the output layer what we end up with is an encoder and a decoder for our input data.
- We can use just the encoder and attach it to the beginning of a new NN and use it to reduce the dimension of the input data.
- We can use just the encoder to reduce all our input data and then use the new input with faster training time (smaller dimensions)
- We can use the whole Autoencoder as a noisy filter for our data, worsening the training data to obtain a more general model. 

---
# Original Files:
![[Pasted image 20220819143150.png]]