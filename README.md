# 6H-TMV-CNN

This repository contains the code for the 6H-TMV-CNN model, a convolutional neural network designed for segmenting and classifying Tobacco Mosaic Virus (TMV) assemblies in microscopy images.

## Overview

The model classifies transmission electron microscopy images of 6H-TMV into four categories:
- Background
- Multi-layer TMV assemblies
- Single-layer hexagonally packed TMV
- Single-layer square packed TMV

## Requirements

- Python 3.10+
- PyTorch
- PyTorch Lightning
- Weights & Biases (wandb)
- NumPy
- Pillow
- Matplotlib
- torchvision

## Dataset Structure

The labelled dataset is organized as follows: 
```
Labelled_Images/
├── background/
├── multi/
├── single-hex/
└── single-square/
```

## Training

The model training process includes:
1. Automatic data splitting (80% training, 20% validation)
2. Mask generation for segmentation
3. Training using PyTorch Lightning
4. Progress tracking with Weights & Biases

## Usage

A pre-trained model checkpoint is available in the `checkpoints/` directory.

To use the model:
1. Load the pre-trained checkpoint using PyTorch Lightning
2. Run inference on microscopy images using the provided inference script
3. View the segmentation results with color-coded classifications

The model has been trained on a specific set of 6H-TMV microscopy images and is optimized for similar image conditions.

## Model Architecture

The CNN architecture is based on a U-Net structure with:
- Encoder path with convolutional and pooling layers
- Skip connections for preserving spatial information
- Decoder path with upsampling and concatenation
- Final segmentation head for pixel-wise classification

## Model Output

The model produces a segmentation map with the following color coding:
- Green: Background
- Blue: Multi-layer assemblies
- Red: Single-layer hexagonal packing
- Yellow: Single-layer square packing

## Citation

Paper is available at https://www.biorxiv.org/content/10.1101/2024.12.26.630424
