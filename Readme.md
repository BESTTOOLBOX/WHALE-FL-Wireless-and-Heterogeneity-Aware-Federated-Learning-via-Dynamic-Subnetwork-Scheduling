# WHALE-FL

## Overview

Due to permission issues, this code repository is still being optimized and updated. The staged versions are not the final versions.

The WHALE-FL codebase is divided into two main parts:
1. **On-Server**: Used for emulation and large-scale experiments on servers or hosts.
2. **On-Device**: Used for training and testing models directly on actual devices.

## Structure

### On-Server
This part is intended for running emulation experiments on servers or high-performance machines. It allows for simulating federated learning environments and testing the performance and accuracy of different models and algorithms.

### On-Device
This part of the code is designed to be executed on actual devices such as mobile phones, tablets, or IoT devices (Based on Linux). It focuses on federated learning scenarios where models are trained locally on the device's data.

## Usage

### On-Server Usage Examples

#### Example 1: Training ResNet18 on CIFAR10

```bash
python train_main.py --data_name CIFAR10 --model_name resnet18 --control_name 1_20_1_non-iid-2_fix_a2-b8_bn_1_1 --id Resnet18@CIFAR10 --alpha 10 --beta 0.2 --gama 1 --losstarget 0.005 --deltalossth 0.2 --quanti_mode linear --linear_arg 2.5

data_name: The dataset to be used (e.g., CIFAR10).
model_name: The model architecture to be trained (e.g., resnet18).
control_name: The configuration string for the experiment.
id: Identifier for the experiment.
alpha, beta, gama: Hyperparameters for the training process.
losstarget: Target loss for the training process.
deltalossth: Threshold for the change in loss.
quanti_mode: Quantization mode (e.g., linear).
linear_arg: Argument for the linear quantization mode.
```

#### Example 2: Training a Convolutional Model on MNIST with Dynamic System

```bash
python train_CNN_Resnet_dynamic.py --data_name MNIST --model_name conv --control_name 1_20_1_non-iid-2_fix_a2-b8_bn_1_1 --id CNN@MNIST --alpha 5 --beta 0.2 --gama 2.5 --losstarget 0.0001 --deltalossth 0.5 --quanti_mode linear --linear_arg 9

data_name: The dataset to be used (e.g., MNIST).
model_name: The model architecture to be trained (e.g., conv).
control_name: The configuration string for the experiment.
id: Identifier for the experiment.
alpha, beta, gama: Hyperparameters for the training process.
losstarget: Target loss for the training process.
deltalossth: Threshold for the change in loss.
quanti_mode: Quantization mode (e.g., linear).
linear_arg: Argument for the linear quantization mode.
```

### On-Device Usage Example

```bash
python train_classifier_fed.py --data_name MNIST --model_name conv --control_name 1_1_0.1_iid_fix_a2-b8_bn_1_1

data_name: The dataset to be used (e.g., MNIST).
model_name: The model architecture to be trained (e.g., conv).
control_name: The configuration string for the experiment.
```

## Installation

To run the WHALE-FL code, you need to have Python installed. It is recommended to create a virtual environment to manage dependencies.

## Dataset Preparation

Ensure that the datasets (e.g., CIFAR10, MNIST, WikeText2, HAR) are available and correctly placed in the data directory or specified path in your configuration.

## Additional Information

The "device_list_example.csv" file provides examples of communication and computation times for various clients in the CNN@MNIST task. This can be used to understand and optimize the performance of federated learning tasks.

## License
This project is currently non-licensed.