# Brain-Tumor-Detection-System

# Project Overview
This project implements a CNN-based model to classify brain MRI images as tumorous or healthy. Designed for efficiency, the system works well on standard hardware without requiring specialized GPUs.

Key Features:

🧠 Binary classification with 88.7% test accuracy

🔁 Data augmentation to handle dataset imbalance

⚡ Streamlined preprocessing pipeline

🌐 Gradio-based web demo for easy testing

📦 Lightweight model optimized for CPU execution


# Model Flow

```
graph LR
A[Raw MRI] --> B(Preprocessing)
B --> C[Augmentation]
C --> D[Model Training]
D --> E[Evaluation]
E --> F[Web Deployment]
```


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


# Preprocessing Pipeline:

Cropping : Extract brain regions from raw MRI scans

Resizing : Standardize images to 240×240×3 pixels

Normalization : Scale pixel values to [0, 1]

Augmentation : Rotation, flipping, zooming (20° range)


# Installation
# Prerequisites

Python 3.8+

TensorFlow 2.x

OpenCV

# Setup Instructions

```
# Save the model in .h5 file(model.h5) in models folder 

# Clone the repository
git clone https://github.com/Rahul495-hub/Brain-Tumor-Detection-System.git
cd Brain-Tumor-Detection-System

# Create virtual environment (recommended)
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate     # Windows

# Install dependencies
pip install -r requirements.txt
```
# Running the Web Demo

```
python app.py
```



















