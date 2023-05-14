## BP #6 - Hyperparameters

# Hyperparameters and their Importance to Deep Learning Models
---
---
## Epochs
---
The number of ***Epochs*** controls the number of times the entire training dataset is passed through the neural network during training. An epoch is defined as one complete pass through the entire training dataset.

During each epoch, the weights of the neural network are updated based on the error (or loss) between the predicted output and the true output of the model. The training process continues for a fixed number of epochs or until a convergence criterion is met.

Increasing the number of epochs can improve the performance of the neural network by allowing it to see the training data more times and fine-tune the weights to better fit the training data. However, increasing the number of epochs beyond a certain point may lead to overfitting (this is where the model performs well on the training data but poorly on new data).

The optimal number of epochs is typically determined by using techniques such as cross-validation or by monitoring the validation loss during training and stopping the training when the validation loss stops improving.

## Batch Size
---
The ***Batch Size*** controls the number of training examples that are processed together in each iteration of the training process.

A larger batch size can lead to faster training times because the model can process more data in each iteration. However, larger batch sizes also require more memory and may be more prone to overfitting.

Conversely, a smaller batch size may result in slower training times due to the model processing less data in each iteration. This can result in lesser overfitting because the model has more opportunities to adjust the weights.

## Metrics - Accuracy & Error Rates
---
The two main metrics considered for this assignment have thus far been ***Error Rate*** and ***Accuracy***

**Accuracy** is the proportion of correct predictions over all predictions, while **Error Rate** is the proportion of incorrect predictions over all predictions.

From initial testing, I have found that the choice between accuracy and error rate depends on the problem being considered. For example, if the two classes in a binary classification problem are imbalanced (one class has many more examples than the other), accuracy may be a misleading metric since the model could simply predict the majority class all the time and still achieve a high accuracy. In these cases, error rate may be a more appropriate metric since it captures the number of incorrect predictions, which is more important in this scenario.

Conversely, if the two classes in a binary classification problem are balanced, then accuracy may be an appropriate metric.

## Learning Rate
---
The ***Learning Rate*** is a hyperparameter that determines the step size or rate at which the model's weights are updated during training. A higher learning rate can help the model converge faster but may lead to overshooting and instability, whilst a lower learning rate may help the model converge more accurately but at the expense of a longer training time. This hyperparameter is denoted as ```base_lr``` in fastai and can be changed by passing it as an argument to the ```fine_tune()``` function (although fastai has a default value for this which seems to produce good results from initial testing).

## Weight Decay
---
***Weight Decay*** is a regularization technique that adds a penalty to the loss function based on the magnitude of the model's weights. This penalty encourages the model to learn simpler weight values, which can help to prevent overfitting. Weight decay is controlled by a hyperparameter that is denoted as ```wd``` in fastai, which determines the strength of the penalty. As with ***Learning Rate***, this hyperparameter has a default value in fastai which seems to produce good results from initial testing.

## Dropout
---
***Dropout*** is a regularization technique that randomly sets some units to zero in a neural network layer during training to prevent overfitting. Dropout is controlled by a hyperparameter that is denoted as ```ps``` in fastai, which determines the probability of dropping out a unit. A higher dropout rate means that more units will be dropped out, which can help prevent overfitting but may also make the model less accurate. This hyperparameter is another that has a default value in fastai which appears to produce reasonable results.