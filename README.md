# FinalNet CNN for CIFAR-10

This repository contains the implementation of a custom CNN architecture called FinalNet, designed for the CIFAR-10 dataset. The goal of this project is to achieve better classification accuracy than the YourNet and LeNet models.

## Table of Contents

- [Overview](#overview)
- [FinalNet Architecture](#finalnet-architecture)
- [Implementation Steps](#implementation-steps)
- [Performance](#performance)
- [Dependencies](#dependencies)
- [Usage](#usage)
- [Resources](#resources)

## Overview

The FinalNet model is a convolutional neural network for image classification on the CIFAR-10 dataset, which consists of 60,000 32x32 color images across ten different classes. The architecture is composed of a feature extractor and a classifier. The feature extractor includes a series of convolutional, batch normalization, and activation layers along with max-pooling layers. The classifier contains three fully connected layers with ReLU activations and dropout layers.

## FinalNet Architecture

The architecture consists of the following layers:

| Layer   | Kernel Size | Stride | Padding | Number of Filters |
|---------|-------------|--------|---------|-------------------|
| Conv1   | 11          | 1      | 5       | 16                |
| Conv2   | 7           | 1      | 3       | 32                |
| Conv3   | 5           | 1      | 2       | 32                |
| Conv4   | 5           | 1      | 2       | 64                |
| Conv5   | 5           | 1      | 3       | 128               |
| Max Pool1 | 2         | 2      | 0       | -                 |
| Conv6   | 5           | 1      | 0       | 256               |
| Max Pool2 | 2         | 2      | 0       | -                 |
| Conv7   | 15          | 1      | 0       | 320               |

## Implementation Steps

1. Grab the CIFAR-10 dataset using the PyTorch framework.
2. Start with the YourNet (HW7) model.
3. Modify the architecture to create the FinalNet model.
4. Add a learning rate scheduler and a new optimizer (Adam).
5. Optimize hyperparameters using Optuna.
6. Change the learning rate scheduler to CosineAnnealingWarmRestarts.

## Performance

The FinalNet model achieved the following accuracy:

- YourNet HW7 Best Model with Optimized Hyperparameters: 61%
- FinalNet Trial 22 with Optimized Hyperparameters: 71%
- FinalNet Best Model with New Learning Rate Scheduler (FN-Alpha): 81%

## Dependencies

- PyTorch
- torchvision
- Optuna
- matplotlib

## Usage

Clone the repository and run the code in the Google Colab environment provided in the Resources section. The code trains and evaluates the FinalNet model on the CIFAR-10 dataset. You can modify the hyperparameters and architecture as needed.

## Resources

- [Code (Google Colab)](https://colab.research.google.com/drive/1ZBVs5SRDbNJZVrwdpBqLE3yF6geZPOnU?usp=sharing)
- [CSE532 Final Report](https://drive.google.com/file/d/1n5uy5zjK7gLLfm9X8Fr7P5JZ6TZoUSM4/view)