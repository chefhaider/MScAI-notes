L1 weight decay, also known as L1 regularization, is a technique used in machine learning to prevent overfitting and enhance the generalization of a model. Like L2 regularization, L1 regularization adds a penalty to the loss function, but the penalty is proportional to the absolute values of the model parameters (weights) rather than their squared values.

### Mathematical Explanation

The regularized loss function with L1 weight decay can be written as:

$$ L_{\text{regularized}} = L_{\text{original}} + \lambda \sum_{i=1}^{n} |w_i| $$

where:
- \( L_{\text{original}} \) is the original loss function (e.g., mean squared error for regression, cross-entropy for classification).
- \( \lambda \) is the regularization parameter that controls the strength of the penalty.
- \( w_i \) are the weights of the model.
- \( \sum_{i=1}^{n} |w_i| \) is the sum of the absolute values of the weights.

### How It Works

1. **Penalty on Large Weights**: By adding the sum of the absolute values of the weights to the loss function, L1 regularization penalizes large weights. This encourages the model to keep the weights small.

2. **Sparsity**: L1 regularization tends to drive some weights to exactly zero, effectively performing feature selection. This results in a sparse model where only a subset of the weights (features) have non-zero values.

3. **Generalization**: By reducing the number of non-zero weights, L1 regularization helps in simplifying the model, which can improve its performance on unseen data.

