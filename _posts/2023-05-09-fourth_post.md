## BP #4 - t-SNE and Confusion Matrices

# Deep Learning Model Performance Analysis Using t-SNE & Confusion Matrices
## Background Theory
---


## t-SNE
---
The points of the t-SNE embeddings of the activations scatter plot correspond to an image in the validation image set. This plot provides us a means to visualise the degree of separation between the different classes of images (in the case of the assignment, there are 10 animals or classes).

## Confusion Matrices
---
The confusion matrix is a matrix whose entries (i, j) corresponds to the number of images in a particular class (i) which were prediceted to be in another class (j) by the model. The diagonal entries (i, j=i) correspond to the number of correctly classified images whilst the non-diagonal entries correspond to the misclassified images. The confusion matrix thus provides another means to view the overall performance of the model (through using the validation set of images).
