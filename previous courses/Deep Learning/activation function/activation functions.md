

### Sign Function
- Mathematically undesirable because its derivative is zero everywhere except at infinity.

### Linear Activation
- Does not introduce non-linearity.

### Sigmoid Function
- **Cons:**
  - Gradient saturates towards edges.
  - Not zero-centered: Always produces positive numbers, causing the internal covariate shift of successive layers. This means the function is always shifted towards a mean greater than zero, forcing layers to constantly adapt. As a result, batch learning reduces the variance.

### Tanh
- Zero-centered.
- Still saturates and causes the vanishing gradient problem.

### Common Issue with Tanh and Sigmoid
- Large regions of \( x \) affect small regions of \( y \), amplifying the vanishing gradient problem during backpropagation.

### ReLU (Rectified Linear Unit)
- **Pros:**
  - Not zero-centered but does not have a vanishing gradient.
  - Allows building deeper networks.
  - Piece-wise linearity causes more sparsity and reduced overfitting, as only a few neurons are active.
- **Cons:**
  - Dying ReLU: When weights and biases are supposed to have negative values, no more updates happen. Often related to having a high learning rate.
- *See slides for more details.*

### Leaky ReLU
- Also known as Parametric ReLU, where you can train the alpha which can be learned.

### Other Activation Functions
- **Exponential Linear Units (ELU):**
  - A smooth function on the negative half-space that slowly decays.
- **Scaled ELU:**
  - Eliminates the problem of covariate shift. (Batch normalization can also be used to fix this issue).
