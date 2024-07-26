
```python
import numpy as np

# Sigmoid activation function and its derivative
def sigmoid(x):
    return 1 / (1 + np.exp(-x))

def sigmoid_derivative(x):
    return sigmoid(x) * (1 - sigmoid(x))

class NeuralNetwork:
    def __init__(self, layer_sizes):
        self.layer_sizes = layer_sizes
        simport numpy as np

# Sigmoid activation function and its derivative
​￼def sigmoid(x):
    return 1 / (1 + np.exp(-x))

​￼def sigmoid_derivative(x):
    return sigmoid(x) * (1 - sigmoid(x))

​￼class NeuralNetwork:
    ​￼def __init__(self, layer_sizes):
        self.layer_sizes = layer_sizes
        self.num_layers = len(layer_sizes)
        self.weights = []
        self.biases = []
        self.initialize_parameters()
    
    # Initialize weights and biases for all layers
    ​￼def initialize_parameters(self):
        ​￼for i in range(self.num_layers - 1):
            self.weights.append(np.random.randn(self.layer_sizes[i], self.layer_sizes[i + 1]))
            self.biases.append(np.random.randn(self.layer_sizes[i + 1]))
    
    # Forward pass
    ​￼def forward_pass(self, X):
        activations = [X]
        z_values = []
        
        ​￼for i in range(self.num_layers - 1):
            z = np.dot(activations[-1], self.weights[i]) + self.biases[i]
            a = sigmoid(z)
            z_values.append(z)
            activations.append(a)
        
        return activations, z_values
    
    # Backward pass
    ​￼def backward_pass(self, X, y, activations, z_values, learning_rate):
        # Output error
        delta = (activations[-1] - y) * sigmoid_derivative(z_values[-1])
        
        ​￼for i in reversed(range(self.num_layers - 1)):
            dW = np.outer(activations[i], delta)
            db = delta
            
            ​￼if i > 0:
                delta = np.dot(self.weights[i], delta) * sigmoid_derivative(z_values[i-1])
            
            self.weights[i] -= learning_rate * dW
            self.biases[i] -= learning_rate * db
    
    # Training function
    ​￼def train(self, X, y, epochs=1000, learning_rate=0.01):
        ​￼for epoch in range(epochs):
            ​￼for i in range(len(X)):
                activations, z_values = self.forward_pass(X[i])
                self.backward_pass(X[i], y[i], activations, z_values, learning_rate)
    
    # Predict function
    ​￼def predict(self, X):
        activations, _ = self.forward_pass(X)
        return activations[-1]

# Example usage
# Network with 2 input neurons, 2 hidden layers with 3 neurons each, and 1 output neuron
layer_sizes = [2, 3, 3, 1]

# Create the neural network
nn = NeuralNetwork(layer_sizes)

# Simple dataset (XOR problem)
X = np.array([[0, 0], [0, 1], [1, 0], [1, 1]])
y = np.array([[0], [1], [1], [0]])

# Train the network
nn.train(X, y, epochs=10000, learning_rate=0.1)

# Test the network
​￼for i in range(len(X)):
    print(f"Input: {X[i]}, Predicted Output: {nn.predict(X[i])}")elf.num_layers = len(layer_sizes)
        self.weights = []
        self.biases = []
        self.initialize_parameters()
    
    # Initialize weights and biases for all layers
    def initialize_parameters(self):
        for i in range(self.num_layers - 1):
            self.weights.append(np.random.randn(self.layer_sizes[i], self.layer_sizes[i + 1]))
            self.biases.append(np.random.randn(self.layer_sizes[i + 1]))
    
    # Forward pass
    def forward_pass(self, X):
        activations = [X]
        z_values = []
        
        for i in range(self.num_layers - 1):
            z = np.dot(activations[-1], self.weights[i]) + self.biases[i]
            a = sigmoid(z)
            z_values.append(z)
            activations.append(a)
        
        return activations, z_values
    
    # Backward pass
    def backward_pass(self, X, y, activations, z_values, learning_rate):
        # Output error
        delta = (activations[-1] - y) * sigmoid_derivative(z_values[-1])
        
        for i in reversed(range(self.num_layers - 1)):
            dW = np.outer(activations[i], delta)
            db = delta
            
            if i > 0:
                delta = np.dot(self.weights[i], delta) * sigmoid_derivative(z_values[i-1])
            
            self.weights[i] -= learning_rate * dW
            self.biases[i] -= learning_rate * db
    
    # Training function
    def train(self, X, y, epochs=1000, learning_rate=0.01):
        for epoch in range(epochs):
            for i in range(len(X)):
                activations, z_values = self.forward_pass(X[i])
                self.backward_pass(X[i], y[i], activations, z_values, learning_rate)
    
    # Predict function
    def predict(self, X):
        activations, _ = self.forward_pass(X)
        return activations[-1]

# Example usage
# Network with 2 input neurons, 2 hidden layers with 3 neurons each, and 1 output neuron
layer_sizes = [2, 3, 3, 1]

# Create the neural network
nn = NeuralNetwork(layer_sizes)

# Simple dataset (XOR problem)
X = np.array([[0, 0], [0, 1], [1, 0], [1, 1]])
y = np.array([[0], [1], [1], [0]])

# Train the network
nn.train(X, y, epochs=10000, learning_rate=0.1)

# Test the network
for i in range(len(X)):
    print(f"Input: {X[i]}, Predicted Output: {nn.predict(X[i])}")
```


