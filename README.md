# Brain-Tumor-Detection-System

# Project Overview
This project implements a CNN-based model to classify brain MRI images as tumorous or healthy. Designed for efficiency, the system works well on standard hardware without requiring specialized GPUs.

Key Features:

🧠 Binary classification with 88.7% test accuracy

🔁 Data augmentation to handle dataset imbalance

⚡ Streamlined preprocessing pipeline

🌐 Gradio-based web demo for easy testing

📦 Lightweight model optimized for CPU execution


# Model Architecture
The custom CNN architecture delivers high performance while maintaining computational efficiency:

```
Input (240, 240, 3)
├── ZeroPadding2D(padding=((3, 3), (3, 3)))
├── Conv2D(32, kernel_size=(7, 7), strides=1, use_bias=False)
├── BatchNormalization()
├── ReLU()
├── MaxPooling2D(pool_size=(4, 4), strides=4)
├── Flatten()
└── Dense(1, activation='sigmoid')
```

# Dataset

The model uses the Kaggle Brain MRI Dataset with augmentation to address class imbalance:

Class	        Original	   After Augmentation

Tumor (Yes)       155              1,085

Healthy (No)       98	               980

Total	            253	             2,065


# Preprocessing Pipeline:

Cropping : Extract brain regions from raw MRI scans

Resizing : Standardize images to 240×240×3 pixels

Normalization : Scale pixel values to [0, 1]

Augmentation : Rotation, flipping, zooming (20° range)
