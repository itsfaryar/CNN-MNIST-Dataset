Here’s the updated README with the provided model structure and results:

---

# MNIST CNN Model

This repository contains a Convolutional Neural Network (CNN) model implemented in Keras to classify handwritten digits using the MNIST dataset. The `MNIST.ipynb` notebook provides a step-by-step guide to building, training, and evaluating the model.

## Dataset Information

The MNIST dataset is a collection of 70,000 handwritten digit images, where:

- **Training set**: 60,000 images
- **Test set**: 10,000 images
- Each image is a grayscale image of size **28x28 pixels**.
- The dataset includes labels for 10 classes (digits from 0 to 9).

This dataset is widely used as a benchmark for image classification tasks in machine learning.

## Model Structure

The CNN model is implemented using Keras and consists of the following layers:

```
_________________________________________________________________
 Layer (type)                Output Shape              Param #
=================================================================
 input_1 (InputLayer)        [(None, 28, 28, 1)]       0

 conv2d (Conv2D)             (None, 28, 28, 32)        320

 conv2d_1 (Conv2D)           (None, 28, 28, 64)        18496

 flatten (Flatten)           (None, 50176)             0

 dense (Dense)               (None, 16)                802832

 dense_1 (Dense)             (None, 10)                170

=================================================================
Total params: 821,818
Trainable params: 821,818
Non-trainable params: 0
```

### Explanation of Layers

1. **Input Layer**: Accepts 28x28 grayscale images.
2. **Convolutional Layers**: Extract spatial features using small kernels.
3. **Flatten Layer**: Converts the 2D feature maps into a 1D vector for the fully connected layers.
4. **Dense Layers**: Learn complex patterns and perform classification.
5. **Output Layer**: Outputs probabilities for each of the 10 digit classes.

## Results

The model was evaluated on the test set, producing the following classification report:

```
Train Predict Report===============

              precision    recall  f1-score   support

           0       0.99      1.00      0.99       980
           1       0.99      0.99      0.99      1135
           2       0.98      0.99      0.99      1032
           3       0.98      0.99      0.99      1010
           4       0.99      0.98      0.98       982
           5       0.98      0.98      0.98       892
           6       0.98      0.99      0.99       958
           7       0.98      0.98      0.98      1028
           8       0.98      0.98      0.98       974
           9       0.98      0.97      0.98      1009

    accuracy                           0.99     10000
   macro avg       0.98      0.98      0.98     10000
weighted avg       0.99      0.99      0.99     10000
```
