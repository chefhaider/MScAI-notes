a function f is convex if the domain dom(f) if f is a convex set and theta with 0<= theta <=1 
the linear interpolation in the output domain would always be greater then the interpolation along the original function

Here's a simplified breakdown of the content, with easy-to-recall bullet points:

#### 10.1 General Interpretation of Convexity:
- Convex function: A line between any two points on the curve will always lie above the function.
- Visual check: If the line doesn’t cross the curve, it's convex.

#### 10.2 Unconstrained Optimization:
- **Goal:** Find the minimum of a convex, differentiable function $f$.
- **Key Equation:** 
  - The optimal point $\mathbf{x}^*$ is found by:  
    $$
    \mathbf{x}^* = \text{arg min}_\mathbf{x} f(\mathbf{x})
    $$
- **Condition for Minimum:**
  - The gradient at the optimal point is zero:
    $$
    \nabla f(\mathbf{x}^*) = 0
    $$
- **Solution Method:**
  - Analytical solutions rare, so use **iterative methods** like **Newton-Raphson**.

#### 10.3 Descent Methods:
- **Core Idea:** Use an iterative process to follow the gradient in the direction of the steepest descent.
  - Update rule:
    $$
    \mathbf{x}^{(k+1)} = \mathbf{x}^{(k)} + t^{(k)} \Delta \mathbf{x}^{(k)}
    $$
- **Key Components:**
  - $\Delta \mathbf{x}^{(k)}$: Search direction at iteration $k$
  - $t^{(k)}$: Step size at iteration $k$

- **Step Size (t):**
  - If too large: Jump too far, oscillation.
  - If too small: Stuck before reaching the minimum.
  - Use **line search** to find an optimal step size, e.g., **Armijo-Goldstein Algorithm**.

- **Search Direction:**
  - Negative gradient is a common direction:
    $$
    \Delta \mathbf{x}^{(k)} = - \nabla f(\mathbf{x}^{(k)})
    $$
  
- **Norm-based Methods:**
  - Different norms change the descent direction.
    - **L2-norm:** Normal steepest descent.
    - **L1-norm:** Coordinate descent (moves along coordinate axes).
    - **L∞-norm:** Moves along 45° diagonals.
  - The direction maximizes the gradient projection on a unit vector:
    $$
    \Delta \mathbf{x} = \text{arg min}_u \{ \nabla f(\mathbf{x})^T \mathbf{u}; ||\mathbf{u}||_p = 1 \}
    $$
  
  - **LP-norm:** Projects gradient on the largest principal component (similar to LDA).

#### Final Direction Formula:
- To compute direction in LP-norm:
  $$
  \Delta \mathbf{x} = - P^{-1} \nabla f(\mathbf{x})
  $$ 

#### Neweton's Methode
Finds the nearest extrema using second order taylor expansion.
compute the gradient of the taylor expansion and set it to zero
this is the same as using gradient descent methode at Lp-norm