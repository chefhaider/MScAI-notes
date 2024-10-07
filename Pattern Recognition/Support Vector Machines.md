
find a decision boundary that separates two classes and also maximises the distance to the nearest point of each .

recap [
svm can be formalised as normsquared of alpha vector. - normal square of the decision boundary and with soft margin we have xi_i which helps move points on the wrong side of the decision boundray to  the correct.
]

## Hard Margin Problem

The hard margin SVM (Support Vector Machine) problem aims to find a decision boundary (hyperplane) that separates two classes of data (labeled +1 and -1) perfectly. Let's break down this problem into simple steps:

### 1. **Decision Boundary**
   - We want to find a line (or plane) that separates the two classes. The equation of this line is:
     $$
     f(\mathbf{x}) = \mathbf{\alpha}^T \mathbf{x} + \alpha_0
     $$
     - **α** is a vector that defines the direction of the line (but not normalized).
     - **α₀** is a constant that shifts the line up or down.

### 2. **Class Constraints**
   - We introduce constraints that make sure the two classes are separated correctly:
     - For class +1 (positive class): $$
       \mathbf{\alpha}^T \mathbf{x}_{+1} + \alpha_0 \geq 1
     $$
     - For class -1 (negative class): $$
       \mathbf{\alpha}^T \mathbf{x}_{-1} + \alpha_0 \leq -1
     $$
   - This means:
     - For a positive class sample, the value computed by the decision rule is greater than or equal to 1.
     - For a negative class sample, the value is less than or equal to -1.

### 3. **Combined Constraint**
   - We combine the constraints for both classes into one equation:
     $$
     y_i \cdot (\mathbf{\alpha}^T \mathbf{x}_i + \alpha_0) \geq 1
     $$
     - Here, **y₁ = +1** for the positive class and **y₁ = -1** for the negative class.
     - This ensures that all samples follow the same rule for classification.

### 4. **Maximising the Margin**
   - **Margin**: The distance between the decision boundary and the nearest points from either class.
   - We want to **maximize** this margin because larger margins lead to better separation. The formula for the width of the margin is:
     $$
     \text{Width} = \frac{2}{||\mathbf{\alpha}||}
     $$
     - The width depends on **α**, the vector defining the hyperplane.

### 5. **Optimization Problem**
   - Instead of maximizing the margin directly, we minimize the inverse of the margin. This simplifies the problem:
     $$
     \min \frac{1}{2} ||\mathbf{\alpha}||^2
     $$
   - This is the **objective function** we aim to minimize.
   - The constraint we need to satisfy is still:
     $$
     y_i \cdot (\mathbf{\alpha}^T \mathbf{x}_i + \alpha_0) \geq 1
     $$

### Summary of Steps:
1. **Define the decision boundary**: $f(\mathbf{x}) = \mathbf{\alpha}^T \mathbf{x} + \alpha_0$
2. **Set class constraints**:
   - For class +1: $\mathbf{\alpha}^T \mathbf{x}_{+1} + \alpha_0 \geq 1$
   - For class -1: $\mathbf{\alpha}^T \mathbf{x}_{-1} + \alpha_0 \leq -1$
3. **Combine constraints**: $y_i \cdot (\mathbf{\alpha}^T \mathbf{x}_i + \alpha_0) \geq 1$
4. **Maximize the margin**: Maximize $\frac{2}{||\mathbf{\alpha}||}$ by minimizing $\frac{1}{2} ||\mathbf{\alpha}||^2$
5. **Solve the optimization problem** with the margin constraint.

