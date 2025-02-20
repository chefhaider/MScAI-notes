https://www.fau.tv/clip/id/23033

the least square method with the partial derivative technique  is applied when the columns are mutually independent. If they are not then we can apply svd or regularization techniques  



---
In the equation you've provided:

$$
X \sim \theta = y \iff \sim \theta = X^+ y
$$


 **Pseudoinverse $X^+$**:
   - The $+$ symbol denotes the Moore-Penrose pseudoinverse of the matrix $X$. It is used to find a least-squares solution to the equation $X\theta = y$ when $X$ may not be a square matrix or may not have full rank.

### Explanation of the Equation

- **$X \sim \theta = y$**:
  - This notation suggests that the product of matrix $X$ and parameter vector $\theta$ is equal to the response vector $y$.

- **$\sim \theta = X^+ y$**:
  - This part states that the estimate of $\theta$ can be obtained by multiplying the pseudoinverse of $X$ by the response vector $y$. This is useful when directly solving $X\theta = y$ is not feasible due to issues like multicollinearity or when $X$ is not a square matrix.


---


Ridge Regression
- we extend the objective function with an additional term constratining the euclidean length - we do that be either, penalising the log likelihood by 
- the problem is non singular even if X^T X is not full rank 
- are not equivariant therefore need to standardise the input 
- the intercept a should not be penalised

Lasso
- mixture of L2 and L1 norm where we are trying to get sparser solutions 
