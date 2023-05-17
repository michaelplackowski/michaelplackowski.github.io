## BP #8 - How Neural Networks Work

# Neural Networks from the Ground Up
---
---
## NN Composition
---
As I have been learning more and more about deep learning, I have become curious about the details of neural networks and what they actually are.

Upon watching [**this**](https://www.youtube.com/watch?v=VMj-3S1tku0) informative and demonstrative video by Andrej Karpathy, I have come to learn about what neural networks are at a fundamental level and how they *learn*.

Neural networks are composed of *neurons* which form *layers*, which from the *network*. In the context of machine learning, Neurons are the most fundamental units of processing which may be defined by some mathematical function. They take inputs from other neurons (or from an external source) and produce an output. Each neuron in the same layer (layers are collections of neurons) have the same bias, which is a threshold that determines when a neuron should *fire*. Neurons also have weightings which are applied to the inputs based on the importance of each. To ensure the output of a neuron is sensible, a clipping or activation function is applied such as the sigmoid or hyperbolic tan functions.

A visualisation of a neural network may be seen below:
![](/images/neural_net2.png "Visualisation of a Neural Network (credit: https://cs231n.github.io/convolutional-networks/)")

## Minimisation of the Loss Function & Parameter Adjustment
---
Once a NN has been formed, the output values which correpsond to the model's predictions are used in conjunction with known truth values (the values we desire the model to output) to compute a loss value (high loss values indicate the model's outputs are dissimilar to the truth values, low loss values indicate the model's outputs are close to the truth values). This is typically done using a loss function such as the ***Cross-Entropy Loss*** function, with a simpler loss function being the ***Mean-Sqaured Error (MSE)***. 

Using the output of this loss function, the gradients of each weight for each neuron may be computed via backpropagation or gradient descent (application of the chain rule from calculus). The sign and magnitude of these gradients indicates how much each parameter should be increased or decreased to minimise the loss. For example, a negative gradient indicates that an increase in it's value would result in a decrease of the model's loss. 

These gradients are added to the parameter values and are typically scaled down to avoid overcorrection. This scaling factor is called the model's learning rate, and is chosen to balance the tradeoff of a small value resulting in a long time for the model to converge, and a large value potentially resulting in oscillations preventing convergence. 

The overall training process of a neural network is as follows:
1. Perform a ***forward-pass*** and compute the loss
1. Perform a ***backward-pass*** (backpropagation/gradient descent) to compute the gradients
1. Update the parameters as per the computed gradients
1. Repeat Steps 1-3 until the loss is minimised

A visualisation of this process may seen below:
![](/images/gradient_descent_algorithm_big.png "Visualisation of Training of a Neural Network (credit: https://www.upgrad.com/blog/neural-network-architecture-components-algorithms/)")