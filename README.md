# AI/ML Cell Nucleus Segmentation Project using U-net archetechture

## Overview
This project implements an end-to-end pipeline for automated cell nucleus segmentation using deep learning. It analyzes microscopy images from the Data Science Bowl 2018 competition and segments cell nuclei using a U-Net architecture.

## Pipeline Components

### 1. Image Classification
- K-means clustering categorizes microscopy images into three types:
  - Brightfield microscopy
  - Histological staining (H&E)
  - Fluorescence microscopy
- Analysis shows fluorescent images yield better segmentation results

### 2. Image Preprocessing
- Standardizes images to 256×256
- Generates ground truth masks from individual mask annotations
- Implements data augmentation (flipping, rotation, resizing, cropping, shearing) to improve training performace

### 3. Model Implementation
- U-Net convolutional architecture with encoding/decoding paths
- Runtime data augmentation during training
- Custom loss function combining binary cross-entropy and Dice coefficient
- Real-time visualization of training metrics
- Implement IoU and Dice coefficient metrics for evaluation
- RLE encoding for competition submission

## Results
- Achieved ~0.45 IoU on validation set (ranked ~300/740 in competition)
- Model performs best on fluorescent images with clear contrast
- Model struggles with poorly defined cell boundaries in brightfield and histology images

## Usage
1. Update file paths in each notebook to match your environment
2. Run notebooks in sequence (classification → preprocessing → training)
3. For inference, load the trained model and apply to new images

## Future Improvements
- Train on full dataset with larger batch sizes
- Develop specialized models for different image types
- Implement post-processing to improve border definition
- Implement post-model classification methods to futher improve precision/recall in a two-step classifier 

## Dependencies
- NumPy, Pandas, scikit-image, scikit-learn
- TensorFlow/Keras
- Matplotlib, seaborn
