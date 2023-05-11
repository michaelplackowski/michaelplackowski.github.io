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

## Perplexity
---
The ***Perplexity*** parameter in t-SNE is a hyperparameter that controls the balance between preserving local and global structure in the low-dimensional embedding (see [Blog Post 4](https://michaelplackowski.github.io/2023/05/10/fourth_post.html) for more details). It is a measure of the effective number of neighbors that each data point should have in the high-dimensional space.

A larger perplexity value means that each data point considers more neighbors in the high-dimensional space, resulting in the algorithm focusing more on preserving the global structure of the data. Conversely, a lower perplexity value means that each data point considers a lesser amount of neighbors, resulting in the algorithm focusing more on preserving the local structure of the data.

As with the other hyperparameters mentioned here, perplexity choice is largely predicated on trial and error to achieve a suitable value that results in greater model performance.

## Number of Iterations
---
A larger value of the ***Number of Iterations*** or ```n_iter```, can lead to a more accurate embedding at the cost of increased computational time. Typically, larger datasets or datasets with high-dimensional data require a greater value of ```n_iter``` to achieve good results.