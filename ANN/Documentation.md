# Neural Network for Handwritten Digits Classification

## Overview
This project implements artificial neural networks to classify handwritten digits using the MNIST dataset. The notebook demonstrates the progression from a simple single-layer network to an improved multi-layer architecture.

## Dataset
- **Source**: MNIST (Modified National Institute of Standards and Technology database)
- **Training samples**: 60,000 images
- **Test samples**: 10,000 images
- **Image format**: 28×28 pixel grayscale images
- **Classes**: Digits 0-9 (10 classes)

## Data Preprocessing

### Normalization
- Divided pixel values by 255 to normalize data to range [0, 1]
- This helps the neural network train more efficiently

### Flattening
- Reshaped each 28×28 image into a 1D vector of 784 features
- Original shape: (60000, 28, 28) → Flattened: (60000, 784)
- Test data similarly flattened: (10000, 28, 28) → (10000, 784)

## Model 1: Simple Neural Network

### Architecture
- **Input layer**: 784 neurons (one for each pixel)
- **Output layer**: 10 neurons (one for each digit class)
- **Activation function**: Sigmoid
- **Single-layer architecture** (no hidden layers)

### Training Configuration
- **Optimizer**: Adam
- **Loss function**: Sparse categorical cross-entropy
- **Metrics**: Accuracy
- **Epochs**: 5

### Results
- Basic performance baseline established
- Confusion matrix generated to analyze prediction errors
- Identified which digits were commonly misclassified

## Model 2: Improved Neural Network with Hidden Layer

### Architecture
- **Input layer**: 784 neurons
- **Hidden layer**: 100 neurons with ReLU activation
- **Output layer**: 10 neurons with Sigmoid activation
- **Multi-layer architecture** improves learning capacity

### Training Configuration
- Same hyperparameters as Model 1 (Adam optimizer, sparse categorical cross-entropy, 5 epochs)

### Results
- **Improved accuracy** compared to the simple model
- Better ability to capture complex patterns in handwritten digits
- Confusion matrix shows reduced misclassification errors
- ReLU activation in hidden layer enables non-linear feature extraction

## Key Techniques Used

1. **Normalization**: Scaling input data for faster convergence
2. **Flattening**: Converting 2D images to 1D vectors for dense layer input
3. **Activation Functions**:
   - **ReLU** (hidden layer): Introduces non-linearity
   - **Sigmoid** (output layer): Outputs probability-like values
4. **Confusion Matrix**: Visual analysis of classification performance
5. **Heatmap Visualization**: Easy identification of problematic digit pairs

## Libraries Used
- **NumPy**: Numerical computations and array manipulation
- **TensorFlow/Keras**: Neural network implementation
- **Matplotlib**: Data visualization
- **Seaborn**: Enhanced heatmap visualization

## Conclusion
The project demonstrates that adding a hidden layer significantly improves classification performance. The hidden layer allows the network to learn hierarchical features that better represent the digit patterns, resulting in higher accuracy on the test set compared to the simple single-layer network.
