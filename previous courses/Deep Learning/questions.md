To incorporate L2 regularization into your loss function \(L(w, x, y)\), you add a term proportional to the square of the norm of the weight vector \(w\). This penalizes large weights and helps prevent overfitting by encouraging the model to keep the weights small.

### L2-Regularized Loss Function
The L2-regularized loss function can be defined as:
\[ L_{\text{L2}}(w, x, y) = L(w, x, y) + \frac{\lambda}{2} \|w\|^2 \]
where \(\lambda\) is the regularization parameter controlling the strength of the penalty.

### Gradient of the L2-Regularized Loss Function
To derive the weight update rule, we need the gradient of the L2-regularized loss function with respect to the weights \(w\). Let \(\nabla_w L(w, x, y)\) be the gradient of the original loss function \(L(w, x, y)\) with respect to \(w\). The gradient of the L2-regularized loss function is:
\[ \nabla_w L_{\text{L2}}(w, x, y) = \nabla_w L(w, x, y) + \lambda w \]

### Weight Update Rule
Given a learning rate \(\eta\), the weight update rule with L2 regularization becomes:
\[ w_{k+1} = w_k - \eta \left( \nabla_w L(w_k, x, y) + \lambda w_k \right) \]
where \(w_k\) represents the weights at iteration \(k\).

### Summary
- **L2-Regularized Loss Function**:
  \[ L_{\text{L2}}(w, x, y) = L(w, x, y) + \frac{\lambda}{2} \|w\|^2 \]
- **Weight Update Rule**:
  \[ w_{k+1} = w_k - \eta \left( \nabla_w L(w_k, x, y) + \lambda w_k \right) \]

By including the L2 regularization term, the weights are penalized in proportion to their magnitude, leading to smaller weights and thus helping to reduce overfitting. This approach encourages the model to generalize better to unseen data, as evidenced by the increase in accuracy from 72% to 81%.

---
To incorporate L1 regularization into your loss function \(L(w, x, y)\), you add a term proportional to the absolute value of the weights. This encourages sparsity in the model weights, where many weights can become zero, effectively selecting features during training.

### L1-Regularized Loss Function
The L1-regularized loss function can be defined as:
\[ L_{\text{L1}}(w, x, y) = L(w, x, y) + \lambda \|w\|_1 \]
where \(\|w\|_1 = \sum_i |w_i|\) and \(\lambda\) is the regularization parameter controlling the strength of the penalty.

### Gradient of the L1-Regularized Loss Function
To derive the weight update rule, we need the gradient of the L1-regularized loss function with respect to the weights \(w\). Let \(\nabla_w L(w, x, y)\) be the gradient of the original loss function \(L(w, x, y)\) with respect to \(w\). The gradient of the L1-regularized loss function is:
\[ \nabla_w L_{\text{L1}}(w, x, y) = \nabla_w L(w, x, y) + \lambda \, \text{sign}(w) \]
where \(\text{sign}(w)\) is the element-wise sign function, which returns \(1\) for positive elements, \(-1\) for negative elements, and \(0\) for zero elements.

### Weight Update Rule
Given a learning rate \(\eta\), the weight update rule with L1 regularization becomes:
\[ w_{k+1} = w_k - \eta \left( \nabla_w L(w_k, x, y) + \lambda \, \text{sign}(w_k) \right) \]
where \(w_k\) represents the weights at iteration \(k\).

### Summary
- **L1-Regularized Loss Function**:
  \[ L_{\text{L1}}(w, x, y) = L(w, x, y) + \lambda \|w\|_1 \]
- **Weight Update Rule**:
  \[ w_{k+1} = w_k - \eta \left( \nabla_w L(w_k, x, y) + \lambda \, \text{sign}(w_k) \right) \]

By including the L1 regularization term, the weights are penalized in proportion to their absolute value, which encourages sparsity in the model. This can lead to simpler models with fewer non-zero weights, improving interpretability and potentially reducing overfitting by effectively performing feature selection.