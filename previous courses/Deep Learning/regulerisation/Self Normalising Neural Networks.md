

- **Purpose:** 
  - Address stability problems in Stochastic Gradient Descent (SGD).

- **Key Element:**
  - **SeLU (Scaled Exponential Linear Unit)** + **Specific Weight Initialization**

- **SeLU Function:**
  - \( f(x) = \lambda \left\{
    \begin{array}{ll}
    x & \text{if } x > 0 \\
    \alpha (\exp(x) - 1) & \text{otherwise}
    \end{array}
    \right. \)
  - Constants: 
    - \( \lambda_{01} = 1.0507 \)
    - \( \alpha_{01} = 1.6733 \)
    - For mean (\(\mu\)) = 0 and standard deviation (\(\sigma\)) = 1

- **Benefits:**
  - Keeps mean (\(\mu\)) and standard deviation (\(\sigma\)) of activations near 0 and 1 throughout the network.
  - Leads to stable activations and stable training.

- **Dropout Modification:**
  - Instead of dropping neurons to zero, drop to \( -\lambda \cdot \alpha \).

- **Affine Transform:**
  - Used to restore variance and mean.

- **Similarity:**
  - Conceptually similar to **Batch Normalization**.