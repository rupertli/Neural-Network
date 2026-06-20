# Activation Functions in Neural Networks
Based on :

https://www.geeksforgeeks.org/machine-learning/activation-functions-neural-networks/
## About functions and relationships to other parts
In a neural network, data is inputed and stored on multiple nodes in the structure of `x1`, `x2`, `x3`, et cetera. Then, weights (`w1`, `w2`, `w3`) are assigned to nodes randomly pre-training. During training, weights can be adjusted through trial and error, reaching the best weight after training. 

In each node, there are two parts: 
1. $z = \Sigma w_{i}x_{i} + b$ where $b$ stands for bias.
2. $f(z)$, which is an activation function for the neural network. We will expand on the types of $f(z)$ below.

Conventionally, there are several rows of hidden layers in a neural network. For each layer, the activation function is the same.
### Importances to non-linearity
1. Most problems in real life are not linear
2. Neural networks are more capable of handling complex problems
3. They ensure networks can model advanced problems like image recognition, NLP and speech processing.
   
## Types of activation functions
### Linear activation functions
A most conventional choice would be the Linear activation function. It is resembled by the straight line of 
$$
    y = x
$$
Even though this choice can be used in a variety of circumstances, its problem of being simply linear makes it a problem when dealing with non-linear data. So, other forms of non-linear activation functions have become a more practical choice in comparison.
### Non-linear activation programs
- Sigmoid activation
  
  Sigmoid activation can be expressed by
  $$
  A = \frac{1}{1 + e^{-x}}
  $$ 
  This is a good choice, because the range of the function is $(0, 1)$, and it is rather useful for gradient-based output programs.
- Tanh activation
  
  Tanh activation is based on the function of 
  $$
  f(x)= tanh(x) = \frac{2}{1 + e^{-2x}}-1
  $$
  This makes sure that the data is centered between the values of $(-1, 1)$
- ReLU Activation(Rectified Linear Unit)
  
  ReLU activation is defined by 
  $$A(x) = \mathrm{max}(0, x)$$
  Where $A(x)$ is equal to 0 when $x$ is negative, and $A(x)$ is positive when $x$ is positive.

  Commonly used in hidden layers for faster training and better performance. In addition, the use of ReLU can prevent problems such as the Vaishing Gradient problem. 
- Leaky ReLU
  
  Leaky ReLU is different to the conventional ReLU activation function, because it allows a small negative slope.
  $$
  f(x) = \begin{cases}
  x & \text{if } x > 0 \\
  \alpha x & \text{if } x \leq{} 0
  \end{cases}
$$
  The Range is $(-\infty, \infty)$. It is prefered instead of ReLU in some cases because of the streamlined gradient flow.
- Softplus function
  
  The Softplus function is defined as 
  $$
  A(x) = \mathrm{log}(1 + e^x)
  $$
  The Softplus function is non-linear. It is in the boundary of $(0, \infty)$, but without the hard zero threshold and is perfectly continuous and smooth.
### Exponential Linear Units
- ELU function
  
  ELU (Exponential Linear Unit) is a non-linear activation function that improves learning speed and helps reduce the vanishing gradient problem. It behaves like ReLU for positive inputs but allows smooth negative values.
  $$
  f(x) = \lambda\begin{cases}
   x,    \,\,\,\,\,\,\,\,\,\, x > 0\\
   \alpha (e^x-1), \,\,\,\,\,\,\,\,\,\,x \leq 0

  \end{cases}
  $$
  Where the $\lambda \approx 1.05$ is the scaling factor and the $a \approx 1.67$

  The ELU is useful because it can reduce the need for batch normalization in some cases, and also works extremely well in deep connected networks.

### Output layer activation functions
- Sigmoid
  Can be expressed as
  $$
  \sigma(x) = \frac{1}{1+e^{-x}}
  $$
  Commonly used in binary classification, or sorting between two types of data.
- Softmax function
  
  Softmax function is used for multi-class classification and converts raw output scores into probabilities for each class.
  Transforms outputs into values between 0 and 1, and ensures all probabilities sum to 1.
