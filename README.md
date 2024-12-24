# LeNet-5 digit-classifier reimplementation with custom classes

## contents
- [about](#about)
- [features](#features)
- [results](#results)

## about
this is a reimplementation of LeCunn's 1998 influential paper ["Gradient Based Learning Applied to Document Recognition"](http://vision.stanford.edu/cs598_spring07/papers/Lecun98.pdf) which introduced LeNet-5, a low-parameter, CNN-based neural network to classify handwritten digits 0-9.

## features

### built from scratch using only PyTorch's tensor operations:
- custom convolution layer implementation
- custom average pooling layer
- custom loss function
- custom optimizer

### follows the original 1998 paper's specifications exactly:
- network architecture (conv5x5 -> avgpool -> conv5x5 -> avgpool -> fc -> rbf -> pred)
- hyperparameter values (though they didn't reveal some of their values)
- weight initialization method 
- loss function and optimizer choice (maximum a posteriori loss and SDLM optimizer)
- trained and validated on MNIST dataset (60,000 training samples, 10,000 validation samples)

## results

### model performance
after training for 2 epochs on the MNIST dataset (60,000 training samples), the model achieved:
- macro F1 sore: 0.964 (current state of the art models achieve around 0.99)
- per-digit F1 scores:
  | Digit | F1 Score |
  |-------|----------|
  | 0     | 0.980    |
  | 1     | 0.990    |
  | 2     | 0.960    |
  | 3     | 0.955    |
  | 4     | 0.979    |
  | 5     | 0.979    |
  | 6     | 0.955    |
  | 7     | 0.955    |
  | 8     | 0.938    |
  | 9     | 0.950    |

#### highlights 
- training converged in just 2 epochs 
- consistent F1 scores above 0.93 across all digits

### training visualization
#### loss over time (epoch 1)
![loss-over-time](https://github.com/user-attachments/assets/c120031b-8aae-4a7b-987b-22330ea578dc)

### model predictions (before/after)
#### before training
![Pre-training Predictions](https://github.com/user-attachments/assets/88bb8314-6cfc-4ae2-89bb-8a9e44505977)

#### after training
![Post-training Predictions](https://github.com/user-attachments/assets/91b42650-4e7f-4e7e-a672-407cdf0683d4)


