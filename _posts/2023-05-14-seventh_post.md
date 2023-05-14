## BP #7 - Neural Net Foundations

# The Math that Makes NNs Work
---
---
## Many Rectified Linear Functions
---
Lecture 3 of Jeremy Howard's fastai course covered some interesting mathematical foundations of Neural Networks. In particular, rectified linear functions which allow for ensuring that a function never goes below and/or above a set value (e.g. lower bound of 0, upper bound of 1). These functions can also be combined infinitely many times, with their parameters being able to be adjusted automatically via minimising loss functions such as the mean squared error (MSE) through gradient descent. This allows for a deep learning model to be trained.

## Matrix Multiplication
---
Matrix multiplication appears to be integral to neural networks due to GPUs being well suited at performing matrix operations, allowing for faster computations. Something interested covered in the lecture was Jeremy demonstrating creating a neural net by combining two linear regressions on Excel data to tune randomised parameters. He did this using matrix multiplication.

## Image Models
---
In the lecture, Jeremy also spoke upon different image models and their respective performance in terms of computational time and accuracy. This can be found [**here**](https://www.kaggle.com/code/jhoward/which-image-models-are-best/notebook#Training-results), with the results of using various models on a training set shown below.

![](/images/imageModelsPerformance.png "Performance of Various Image Deep Learning Models on a Training Set (credit: https://www.kaggle.com/code/jhoward/which-image-models-are-best/notebook#Training-results)")