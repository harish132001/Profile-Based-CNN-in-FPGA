# Profile-Based-CNN-in-FPGA

# MNIST CNN - Vitis HLS Implementation

This repository contains an implementation of a Convolutional Neural Network (CNN) trained on the MNIST dataset, designed for FPGA acceleration using Vitis HLS.

## 🧠 Overview

The goal of this project is to run a lightweight CNN on handwritten digit images (MNIST) and prepare the model for FPGA execution using HLS (High-Level Synthesis). It includes:

- CNN model definition
- Training and testing scripts (Python)
- Conversion of weights to `weight.hpp`
- Vitis HLS-compatible C++ implementation
- OpenCV integration for image input

## 📁 Project Structure

MNIST_CNN/ 
├── cnn.cpp # CNN main implementation for HLS 
├── cnn.hpp # Header file for CNN 
├── testbench.cpp # Testbench for simulation in HLS 
├── weight.hpp # Weights generated from trained model 
├── scripts/ 
│ ├── generate_weights.py # Converts model weights to HLS-friendly format 
│ └── train_model.py # Trains CNN model on MNIST 
├── images/ # MNIST sample images for simulation 
├── README.md # This file


## ⚙️ Requirements

### Software:
- Python 3.8+
- Vitis HLS 2023.1
- OpenCV (for both Python and C++)
- NumPy
- TensorFlow or PyTorch (for training)

Install dependencies:
bash
```
pip install -r requirements.txt
```
Hardware:
FPGA board (e.g., Zynq ZC706)

Xilinx Vitis toolchain

🧪 How to Run
1. Train the CNN model

cd scripts
-----------------------
|python train_model.py|
-----------------------

This script will train the model and save the weights.

2. Generate the weights header file
----------------------------
|python generate_weights.py|
----------------------------

3. Run Vitis HLS simulation
Open Vitis HLS and create a new project:

Add mnist.cpp, mnist.hpp, and mnist_tb.cpp
Add profile files for weight updation
Set top function to main() or your designated top function

Run C simulation and C synthesis

4. Image Input Testing
Place MNIST test images inside the images/ directory. The testbench will load and process them using OpenCV.

🛠️ Customization:

You can modify the following:

Number of layers/filters in train_model.py

Precision and fixed-point settings in mnist.hpp

Input image sources in mnist_tb.cpp
