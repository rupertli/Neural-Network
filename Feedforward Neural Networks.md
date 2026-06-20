# Feedforward Neural Networks
Based on:  
https://www.geeksforgeeks.org/deep-learning/feedforward-neural-network/ and https://zhuanlan.zhihu.com/p/405658103
## Structure of a Feedforward Neural Network
1. Input Layer: The input layer consists of neurons that receive the input data. Each neuron in the input layer represents a feature of the input data.
2. Hidden Layers: One or more hidden layers are placed between the input and output layers. These layers are responsible for learning the complex patterns in the data. Each neuron in a hidden layer applies a weighted sum of inputs followed by a non-linear activation function.
3. Output Layer: The output layer provides the final output of the network. The number of neurons in this layer corresponds to the number of classes in a classification problem or the number of outputs in a regression problem.
## Evaluation of a neural network
|      |True | False|
|------|-----|------|
|True|True Positive|False negative
|False|False Positive|True negative

Where the top is the predicted value, and the left side is the actual value.

- Accuracy
  
  Accuracy is defined by the number of correctly classified items in a list.
  $$
  A = \frac{TP+TN}{TP+FP+TN+FN}
  $$
  Accuracy should be used only when the number of items in each type have mostly a uniform distribution. In cases where one type of outcome is significantly larger than another, use other types of concepts to determine accuracy.
- Precision
  
  Precision is defined by the number of $TP$ (True positives) in all the determined $P$ (Positives).
  $$
  P = \frac{TP}{TP+FP}
  $$
  Used when the consequences of determining a negative wrongly as a positive.($FP$). For example, if a system identifies a patient without cancer as one with cancer ($FP$), the consequences are high.

- Recall
  
  Recall is defined by the number of $TP$ in all the actually positive situations ($TP+ FN$)
  $$
  R = \frac{TP}{TP+FN}
  $$
  Recall should be used when the consequences of determiningg a positive as a negative ($FN$) is high. For example, wrongly determining a patient with COVID-19 as without the disease has high consequences due to the contagiousness of the disease.

- F1 Score
  
  A F1 score is the weighted mean of the Recall and Precision
  $$
  F_{1} = \frac{2 \times P \times R}{P + R}
  $$
  Here, the F1 score can be used in most situations, and the higher the $F_{1}$ score, the more robust the model is.

  A harmonic mean is the inverse value's mean, and then inversed again.
  $$
  H_{m} = \frac{n}{x_{1} + x_{2} + x_{3} + ... + x_{n}}

## Gradient descent algorithms
Gradient Descent is an optimization algorithm used to minimize the error of a machine learning model by updating parameters in the direction of decreasing loss.

## Training a feedforward Neural Network
1. Forward Propagation: During forward propagation the input data passes through the network and the output is calculated.
2.  The loss (or error) is calculated using a loss function such as Mean Squared Error (MSE) for regression tasks or Cross-Entropy Loss for classification tasks. The MSE is expressed as 
   $$
   L(Y| f(x)) = \frac{1}{n}\Sigma_{i = 1}^{N}{(Y_{i}-f(x_{i}))^2}
   $$
3.  In backpropagation the error is propagated back through the network to update the weights. The gradient of the loss function with respect to each weight is calculated and the weights are adjusted using gradient descent.

## Backpropagation
Backpropagation: This algorithm computes the gradient of the loss function with respect to every weight in the network, telling us exactly how to adjust each parameter to improve predictions. Backpropagation is the most important algorithm in deep learning. Without it, training neural networks would be computationally intractable.

Gradient: calculating the derivative of a function. Because this is a multiple-dimension function, so we can treat it as a 3D structure, and the gradient is the derivative of a function. 

Using the gradient, we can then adjust the weights givern through the process of backpropagation, and acquire the best result through the constant fine-tuning of the weights given to each location.
$$
W_{new} = W_{old} - \eta \nabla_{\mathrm{w}}\mathcal{L}
$$

The vanishing gradient problem: Where the model cannot be trained anymore due to a gradient descent of zero rather than any other value. Basically, the gradient is stuck at a point, unable to improve any further. The rule of gradient descent is
$$
\omega \larr \omega - \alpha \times \nabla_{\omega}\Sigma^{m}_{1}L_{m}(\omega)
$$
Where this process is repeated until convergence. However, in a case where a vanishing gradient is reached, the gradient descent may be stuck at a local minima rather than a global one.
