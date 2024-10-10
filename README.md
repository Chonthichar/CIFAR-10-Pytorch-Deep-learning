## CNN with CIFAR-10 Dataset
The CIFAR-10 dataset was used to evaluate the performance of a Convolutional Neural Network (CNN) on a more complex, 10-class image classification problem. Key findings include:

CNN Architecture for CIFAR-10:
The CNN model consisted of:

![Display 20 images in a grid with class names as titles](image_cifar.png)

Three convolutional layers: Each followed by ReLU activation and max pooling.
Conv Layer 1: 32 filters, 3x3 kernel, ReLU, MaxPooling (2x2)
Conv Layer 2: 64 filters, 3x3 kernel, ReLU, MaxPooling (2x2)
Conv Layer 3: 128 filters, 3x3 kernel, ReLU, MaxPooling (2x2)
Fully connected layers: 256 and 128 neurons, with a final layer output of 10 neurons using softmax activation for multi-class classification.
Dropout layers (50%) were applied after each fully connected layer to reduce overfitting.
Training and Evaluation:
The model was trained over 30 epochs with three optimizers (SGD, Adam, and RMSProp) and various learning rate schedulers (StepLR, ReduceLROnPlateau, ExponentialLR). Data augmentation techniques, including rotations, flips, and zooms, were used to improve generalization.

The following plots show the comparison of training and test loss/accuracy for different optimizers used in the CNN model on CIFAR-10.
![Training and Test Loss/Accuracy Comparison](Comparison_score.png)

Results:
SGD with ReduceLROnPlateau achieved accuracies between 44.7% and 66.8%, showing improved but fluctuating test accuracy, which suggested some degree of overfitting.
Adam performed poorly, yielding only 9-10% accuracy due to suboptimal hyperparameters or data preprocessing issues.
RMSProp achieved the highest accuracy but displayed overfitting, with training accuracy around 90% and test accuracy around 70%, indicating that further regularization might be needed.
Discussion and Conclusion:
While RMSProp with ReduceLR and ExponentialLR yielded the best training accuracy, significant overfitting was observed, suggesting that a more complex model, such as ResNet or DenseNet, might be better suited for CIFAR-10. Data augmentation played a critical role in improving model stability and performance, especially for CIFAR-10.
