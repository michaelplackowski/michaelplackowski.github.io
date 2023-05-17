## BP #4 - t-SNE and Confusion Matrices

# Deep Learning Model Performance Analysis Using t-SNE & Confusion Matrices
---
---
## t-SNE
---
t-Distrubuted Stochastic Neighbour Embedding or t-SNE, provides a means to visualise high-dimensional data in a low-dimensional format. Unlike Principal Component Analysis (PCA), t-SNE considers small euclidean distances between data points rather than large pair-wise distances.

The points of the t-SNE embeddings of the activations scatter plot correspond to an image in the validation image set. This plot provides us a means to visualise the degree of separation between the different classes of images (in the case of the assignment, there are 10 animals or classes for Q2).

An example of t-SNE and PCA may be seen below:
![](/images/mnist-visualization-code-output-01.png "Example of t-SNE and PCA (credit: https://in2techs.com/mnist-visualization-using-pca-and-tsne-in-python/)")

Mathematically speaking, t-SNE first considers high-dimensional space where each point has a Gaussian centred over it within which the density of other data points is obtained (with the value normalised). The result of this is a set of probabilities that measure the similarity between pairs of points (this may be considered as the probability distribution over pairs of points where the probability of picking a pair of points is proportional to their similarity). Large probability values indicate that the pair of points are close together, with low probability values indicating otherwise. A similar process is followed but for a low-dimensional space using a Student-t distribution with 1-degree of freedom. These sets of probabilities for both the high and low-dimensional spaces can then be compared. This is done using the [***Kullback Leibler Divergence***](https://en.wikipedia.org/wiki/Kullback%E2%80%93Leibler_divergence) of the two probability distributions, which is minimised to obtain a 2D representation that better represents the actual high-dimensional local structure of the data points in the map.

For further details, see this [**YouTube video presented by Laurens van der Maaten from Delft University of Technology at a Google TechTalk**](https://www.youtube.com/watch?v=RJVL80Gg3lA).

## Confusion Matrices
---
The confusion matrix is a matrix whose entries (i, j) corresponds to the number of images in a particular class (i) which were predicted to be in another class (j) by the model. The diagonal entries (i, j=i) correspond to the number of correctly classified images whilst the non-diagonal entries correspond to the misclassified images. The confusion matrix thus provides another means to view the overall performance of the model (through using the validation set of images).

An example of a multiclass confusion matrix may be seen below:
![](/images/confusion_matrix.png "Example of a Multi-Class Confusion Matrix (credit: https://in2techs.com/mnist-visualization-using-pca-and-tsne-in-python/)")
