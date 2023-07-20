# Machine learning
-**Explain the bias-variance trade-off in the context of Machine Learning and Regression models**
  - It refers to the relationship between the model's ability to capture the complexity of the data (variance) and its tendency to make systematic errors or assumptions (bias).
  - **Bias**: Bias measures how far off the predictions of a model are from the true values, on average, when trained on different datasets. High bias indicates that the model oversimplifies the underlying relationships in the data and may underfit. In such cases, the model may miss important patterns or exhibit systematic errors, resulting in poor performance.
  - **Variance**: Variance quantifies the variability of model predictions when trained on different datasets. High variance indicates that the model is sensitive to the specific training data and captures noise or random fluctuations. This can lead to overfitting, where the model performs exceptionally well on the training data but fails to generalize to unseen data
  - **The bias-variance trade-off **arises from the challenge of finding the right level of model complexity. Models with high complexity, such as those with many parameters or flexible structures, have the potential to capture intricate patterns in the data but are more prone to overfitting and high variance. On the other hand, models with low complexity, such as those with fewer parameters or simple structures, are less likely to overfit but may have higher bias and struggle to capture complex relationships.
  - The goal is to strike a balance between bias and variance by selecting an optimal level of model complexity. This can be achieved through techniques like **cross-validation, regularization, and model selection methods**. Cross-validation helps evaluate the model's performance on unseen data, enabling the identification of the sweet spot that minimizes both bias and variance.

- **How does Regularization help in a regression model**?
  - Overfitting prevention
  - Model complexity control
  - Feature selection and interpretation

# Kmeans
- **working principle**
- Partitioning: The algorithm partitions the data into K clusters, where K is a predefined number chosen by the user.

- Centroid-Based: It assigns each data point to the cluster whose centroid (mean) is closest in terms of Euclidean distance.

- Iterative Optimization: K-means iteratively updates the cluster centroids and reassigns data points until convergence. The goal is to minimize the within-cluster sum of squares, which represents the distance between data points and their assigned centroids.

- **Advantages of K-means**:
  -Simplicity: K-means is easy to understand and implement.
  -Scalability: It performs well on large datasets and can handle a large number of variables.
  -Efficiency: K-means has a fast runtime, making it efficient for many applications.
  -Interpretability: The resulting clusters and centroids can provide insights and interpretability.

- **Disadvantages of K-means**:
  - Initialization Sensitivity: K-means is sensitive to the initial placement of cluster centroids, which can lead to different outcomes.
  - Fixed Cluster Number: The user needs to specify the number of clusters (K) in advance, which may not always be known or easily determined.
  - Sensitive to Outliers: K-means can be influenced by outliers, as they can significantly impact centroid positions and cluster assignments.
  - Limited to Linear Boundaries: K-means assumes that clusters are spherical and have a similar size, making it less effective for complex or non-linear data distributions.

# Overfiting and underfiting
- Overfiting: good at training set, bad on test set, which means it's ability to **generalized** is bad
  - High variance
  - correction:
    - Regularization: L1, L2
    - Data augmentation ---more generlaization
    - Dropout
    - Early stopping  
- Underfiting: perfrom average at training set, bad on test set
  - High bias ($\epsilon$)
  - correction:
    - complex model
    - featrue engineering, increase effiectly feature
    - hyperparameter tuneing
    - less dropout
- **bias-variance trade-off**
