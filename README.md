Potato leaf disease detection  Using a Custom Convolutional Neural Network
Project Overview

This project focuses on multi-class potato leaf disease classification using a custom-built Convolutional Neural Network (CNN) implemented in TensorFlow and Keras.

The model was inspired by an existing baseline architecture, with structural modifications introduced to improve regularization and address class imbalance.

Model Architecture

A custom Sequential CNN model was designed with the following characteristics:

Input size: 256 × 256 × 3

Image resizing and rescaling included within the model

Data augmentation layers integrated into the training pipeline

Five convolutional blocks

Increased depth using multiple 64-filter convolution layers

Dropout layers added after convolutional blocks to reduce overfitting

Fully connected dense layer with 64 units

Final softmax output layer for 3-class classification

Architecture summary:

Conv2D (32 filters) → MaxPooling → Dropout

Conv2D (64 filters) → MaxPooling → Dropout

Conv2D (64 filters) → MaxPooling → Dropout

Conv2D (64 filters) → MaxPooling → Dropout

Conv2D (64 filters) → MaxPooling

Flatten

Dense (64 units, ReLU) → Dropout

Dense (3 units, Softmax)

The model was trained from scratch without transfer learning.

Data Preprocessing

Preprocessing steps were embedded directly into the model using Keras preprocessing layers:

Resizing to 256 × 256

Pixel value rescaling (1./255 normalization)

Random horizontal and vertical flipping

Random rotation

Random zoom

Random contrast adjustment

These augmentation strategies were applied to improve generalization and reduce overfitting.

Handling Class Imbalance

Class imbalance was addressed using computed class weights:

Class weights were calculated using compute_class_weight from scikit-learn

The weights were passed during model training

This ensured minority classes contributed proportionally to the loss function

This improved stability compared to the original version of the project where imbalance was not properly handled.

Training Strategy

Optimizer: Adam

Loss Function: Sparse Categorical Crossentropy

Data augmentation applied during training

Dropout regularization used extensively

Class weights applied to mitigate imbalance

Improvements Over Baseline Model

The following modifications were introduced compared to the original reference architecture:

Increased use of 64-filter convolutional layers

Additional dropout layers for stronger regularization

Explicit class imbalance handling using class weights

Integrated augmentation within the model pipeline

These adjustments were made to improve robustness and reduce overfitting.

Results

(Add your evaluation metrics here)

Accuracy:94.36

Conclusion

This project demonstrates the implementation of a custom CNN architecture for skin lesion classification, incorporating structural modifications and class imbalance handling techniques to improve performance over the original baseline model.
