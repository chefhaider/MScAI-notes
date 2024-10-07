SVMs have limitations, too simple to to provide boundaries, non lienarly seperable data cannot be classified, noisy data causes problems

sol? 
mapping into a higher dimension space using a non linear function and then using a linear classifier

- A kernel function is a symmetric funciton that maps a pair of features to a real number.
- kernel matrix is positive semidefinite
see proof


Kernel Problem
	a transformation could be where the points are non linearly seperable

Marcers Theorem:
	Any symmetric function that maps a  feature space to a real space and that is square integrable on its domain  

Kernel Trick
we can derive an alternative algorithim by replacing the kernel function k by another positive semidefinite kernel k'



---
## Kernel Matrix
In the context of Support Vector Machines (SVM) with Kernel Principal Component Analysis (KPCA), the **kernel matrix** plays a crucial role in enabling SVM to operate in high-dimensional feature spaces without explicitly computing the coordinates of the data in that space. Let’s delve into its purpose and the relevant equations.

### Purpose of the Kernel Matrix

1. **Mapping to Higher Dimensions**: The kernel matrix allows SVM to efficiently perform classification tasks in high-dimensional spaces by using kernel functions. This enables the algorithm to find complex decision boundaries that are not possible in the original input space.

2. **Avoiding Explicit Computation**: By using the kernel matrix, we avoid the computational burden of transforming the data points into a high-dimensional space. Instead, we compute the kernel directly from the original data points.

3. **Computing Similarities**: The kernel matrix contains pairwise similarities between the data points in the feature space induced by the kernel function. This is crucial for SVM since it relies on the inner products of the data points.

### Kernel Matrix Definition

Given a set of $N$ data points $\{ \mathbf{x}_1, \mathbf{x}_2, \ldots, \mathbf{x}_N \}$, the **kernel matrix** $K$ is defined as:

$$
K_{ij} = k(\mathbf{x}_i, \mathbf{x}_j)
$$

where $k(\mathbf{x}_i, \mathbf{x}_j)$ is a kernel function that computes the inner product of the data points in the transformed feature space. Common kernels include:

- **Linear Kernel**:
  $$
  k(\mathbf{x}_i, \mathbf{x}_j) = \mathbf{x}_i^T \mathbf{x}_j
  $$

- **Polynomial Kernel**:
  $$
  k(\mathbf{x}_i, \mathbf{x}_j) = (\mathbf{x}_i^T \mathbf{x}_j + c)^d
  $$

- **Gaussian (RBF) Kernel**:
  $$
  k(\mathbf{x}_i, \mathbf{x}_j) = \exp\left(-\frac{||\mathbf{x}_i - \mathbf{x}_j||^2}{2\sigma^2}\right)
  $$

### Using the Kernel Matrix in SVM

The SVM optimization problem involves finding the weight vector $\mathbf{w}$ and the bias $b$ that maximize the margin between two classes. In the context of SVM with kernels, the dual formulation can be expressed as follows:

1. **Lagrangian Dual Formulation**:
   The SVM optimization problem can be formulated in dual form as:

$$
\max_{\boldsymbol{\alpha}} \sum_{i=1}^N \alpha_i - \frac{1}{2} \sum_{i=1}^N \sum_{j=1}^N \alpha_i \alpha_j y_i y_j K_{ij}
$$

subject to:

$$
\sum_{i=1}^N \alpha_i y_i = 0
$$

$$
\alpha_i \geq 0 \quad \forall i
$$

Where:
- $\alpha_i$ are the Lagrange multipliers.
- $y_i$ are the class labels (+1 or -1).
- $K_{ij}$ is the kernel matrix element, representing the similarity between data points.

### Decision Function

Once the optimal $\alpha$ values are found, the decision function for a new point $\mathbf{x}$ can be expressed as:

$$
f(\mathbf{x}) = \sum_{i=1}^N \alpha_i y_i k(\mathbf{x}, \mathbf{x}_i) + b
$$

In this equation:
- The decision function $f(\mathbf{x})$ depends on the kernel evaluations between the new point $\mathbf{x}$ and the support vectors $\mathbf{x}_i$.
- This demonstrates how the kernel matrix allows SVM to utilize data in the transformed feature space without explicitly computing it.

### Summary

The **kernel matrix** in SVM serves to:
- Compute pairwise similarities between data points in a high-dimensional space efficiently.
- Facilitate the use of different kernel functions to capture complex patterns in the data.
- Allow SVM to operate in high-dimensional feature spaces without explicitly mapping the data into those spaces, thereby enhancing computational efficiency and flexibility.
