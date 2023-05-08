## BP #3 - Multi-Class Loss Functions

# Minimising Loss Functions for Improved Models
## Multi-Class Loss Functions
---
Whilst working through the fastai course, I came across the mention of multi-class loss functions. To better understand what these are and their purposes, I researched online - the following summarises the outcome of this learning.

Within the context of fastai, multi-class loss functions are functions which are used to measure the difference between predicted and actual class labels in a multi-class classification problem. These loss functions are minimised during model training for the purpose of improving the accuracy of the model's predictions.

There are many loss functions, with the choice of loss function(s) depending on the nature of the problem (specific characteristics of the problem and the dataset used). However, some common loss functions for multi-class classification include: 

- cross-entropy loss function, 
- the focal loss function, 
- and the label smoothing loss function

## Cross-Entropy Loss Function
---
Currently, the cross-entropy loss function is a popular choice for multi-class classification problems. This loss function measures the difference between the predicted probability distribution and the true probability distribution of the target classes. Mathematically, it is defined as the negative logarithm of the predicted probability of the correct class label, with minimisation of the function done via adjustment of model parameters during the training process.

## Focal Loss Function
---
The focal loss function is a variation of the cross-entropy loss function and is designed to address class imbalance problems in multi-class classification. It does this by assigning higher weights to hard-to-classify examples, providing a potential improvement to the overall accuracy of the model.

## Label Smoothing Loss Function
---
Lastly, the label smoothing loss function is another technique which improves the performance of multi-class classification models by introducing a small amount of noise to the labels during training. This helps prevent overfitting and improves the model's ability to generalize to new data.

## Use in fastai
---
Within the context of fastai, users are able to choose and customize the loss function by using the ***loss_func*** parameter when creating a ***Learner*** object (fastai's API makes this relatively straightforward). A range of pre-defined loss functions for different tasks and scenarios is also provided with fastai, with the option to define custom loss functions offered as well.
