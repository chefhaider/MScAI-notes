

Typically data is noisey and difficult to fit, so we runinto  underfitting (not a good ), or overfitting (high capacity which try to model everything which they observe in the trainig data). We need a compromise between observed and actual 

The Problem can be analysed with **Bias Vairaince Decomposition** - compute a value from an ideal funciton h and is typically associated with some noise

Bias - how far we are from the ground truth
Vairance - Can be explained from the limited size of the dataset. we can always find a model that tries to reduce the bias but we get increased variance.

Model Capacity - Bias and variance relation 
capacity is effected from number of parameter, increasing model capacity increases the bias

---
Model capacity in deep learning refers to the ability of a model to learn a wide variety of functions and represent complex patterns in data. A model with higher capacity can capture more intricate details and nuances of the data, while a model with lower capacity might only be able to represent simpler relationships.

Here are key aspects related to model capacity:

1. **Number of Parameters**: The number of trainable parameters (weights and biases) in a model is a primary determinant of its capacity. More parameters typically mean higher capacity, as the model can potentially represent more complex functions.
    
2. **Network Architecture**: The architecture of the neural network, including the number of layers (depth) and the number of units in each layer (width), influences capacity. Deeper and wider networks generally have higher capacity.
---


variance can be dealt with with increasing more data
model capacity has to match the height of training dataset. if we have too high capacity it can create overfit.

If we have the problem of finite dataset. we try to fix by increasing model capacity, we run into overfit, as initially the test loss may seem to decrease but then it gets very worse
 this is trade of increase in bias for reduction in variance
 
 ---
 Regularization to reduce Overfitting