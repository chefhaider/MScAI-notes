
Bias, deviation of expected model from the true model - how far we are from the ground truth

Variance - explained by limited size of the model, we can always find a model that id flixeble and has good bias but increases the variance. 
 expected value of y_hat - current value of y_hat
The equation you provided is a decomposition of the expected prediction error for a model, which can be broken down into three components: Bias, Variance, and Irreducible Error. This decomposition is often referred to as the Bias-Variance Tradeoff. Let's break down each term in the equation and understand their meanings.

### Equation Breakdown
$$ ED (x) = (ED [ˆyD] − h(x))^2 + ED (ˆyD − ED [ˆyD])^2 + \sigma^2 $$

Where:
- \( ED (x) \): Expected prediction error at a specific point \( x \).
- \( ˆyD \): Prediction of the model trained on dataset \( D \).
- \( h(x) \): True underlying function we aim to approximate.
- \( \sigma^2 \): Irreducible error, the noise in the data.

The equation can be broken down into three parts:

1. **Bias Squared:**
   $$ (ED [ˆyD] − h(x))^2 $$
   - **Explanation:** This term measures the error due to the difference between the expected (average) prediction of the model \( ED [ˆyD] \) and the true function \( h(x) \). It reflects how well the model can capture the true underlying relationship in the data.
   - **Bias:** High bias indicates that the model is too simple and does not capture the complexity of the data well (underfitting).

2. **Variance:**
   $$ ED (ˆyD − ED [ˆyD])^2 $$
   - **Explanation:** This term measures the error due to the variability of the model predictions \( ˆyD \) around their expected value \( ED [ˆyD] \). It reflects how much the predictions would change if we used a different training dataset.
   - **Variance:** High variance indicates that the model is too complex and is overly sensitive to the specific training data (overfitting).

----
