# part-2-cnn-computer-vision

# Part 2: Computer Vision Problem Formulation and CNN Prototype

## Problem Statement

The objective of this project is to build a Convolutional Neural Network (CNN) based computer vision model for manufacturing defect classification using image data.

The dataset contains images of product surfaces categorized into four different classes:
- normal
- scratch
- dent
- stain

The CNN model is trained to automatically classify product images into their correct defect category.

---

# Dataset Information

## Dataset Classes

The dataset contains the following four classes:

1. normal
2. scratch
3. dent
4. stain

## Dataset Summary

| Parameter | Value |
|---|---|
| Total Classes | 4 |
| Total Images | 480 |
| Images Per Class | 120 |
| Image Size | 128 × 128 |
| Training Images | 384 |
| Testing Images | 96 |

---

# Task 1: Problem Identification

## Selected Problem Type: Image Classification

This dataset represents an **Image Classification** problem because:
- Each image belongs to only one category.
- The model predicts one label for the entire image.
- No bounding boxes are provided.
- No pixel-level segmentation masks are available.

The objective is to classify product surface images into one of the four predefined defect categories.

This is not:
- Object Detection
- Semantic Segmentation
- Instance Segmentation

Therefore, Image Classification is the most appropriate computer vision problem type for this dataset.

---

# Task 2: Dataset Exploration

## Dataset Analysis

The following analysis was performed on the dataset:

- Number of classes identified
- Number of images per class counted
- Sample images visualized
- Image dimensions checked
- Dataset balance analyzed

## Class Distribution

| Class | Number of Images |
|---|---|
| normal | 120 |
| scratch | 120 |
| dent | 120 |
| stain | 120 |

The dataset is balanced because each class contains the same number of images.

---

# Task 3: Image Preprocessing

The following preprocessing techniques were applied before model training.

## 1. Image Resizing

All images were resized to:
128 × 128 pixels

This ensures consistent input dimensions for the CNN model.

---

## 2. Pixel Normalization

Pixel values were normalized between 0 and 1 using:

```python
X = X / 255.0
```

Normalization helps improve training stability and model performance.

---

## 3. One-Hot Encoding

Class labels were converted into categorical format using one-hot encoding.

---

## 4. Train-Test Split

The dataset was divided into:
- 80% Training Data
- 20% Testing Data

This allows the model to learn from training data and evaluate performance on unseen test data.

---

## 5. Data Augmentation

The following augmentation techniques were applied:
- Rotation
- Zoom
- Horizontal Flip

Data augmentation improves model generalization and reduces overfitting.

---

# Task 4: CNN Model Creation

## CNN Architecture

The CNN model contains the following layers:

1. Convolution Layer
2. ReLU Activation Function
3. MaxPooling Layer
4. Flatten Layer
5. Dense Layer
6. Dropout Layer
7. Softmax Output Layer

---

## Model Architecture Summary

| Layer | Purpose |
|---|---|
| Conv2D | Feature extraction |
| ReLU | Introduces non-linearity |
| MaxPooling2D | Reduces image dimensions |
| Flatten | Converts feature maps into vector |
| Dense Layer | Learns classification patterns |
| Dropout | Prevents overfitting |
| Softmax Output | Multi-class classification |

---

# Model Parameters

| Parameter Type | Value |
|---|---|
| Total Parameters | 7,392,836 |
| Trainable Parameters | 7,392,836 |
| Non-Trainable Parameters | 0 |

---

# Task 5: Model Training and Evaluation

## Training Configuration

| Parameter | Value |
|---|---|
| Optimizer | Adam |
| Loss Function | Categorical Crossentropy |
| Epochs | 15 |
| Batch Size | 32 |

---

## Model Performance

| Metric | Value |
|---|---|
| Test Accuracy | 71.88% |
| Test Loss | 0.5611 |

---

# Classification Report

| Class | Precision | Recall | F1-Score |
|---|---|---|---|
| normal | 0.54 | 0.88 | 0.67 |
| scratch | 0.43 | 0.25 | 0.32 |
| dent | 0.95 | 0.75 | 0.84 |
| stain | 1.00 | 1.00 | 1.00 |

---

# Result Interpretation

## Best Performing Class

The `stain` class achieved perfect classification performance.

Reason:
- Stain defects have visually distinct color patterns.
- CNN successfully learned these features.

---

## Moderate Performing Class

The `dent` class achieved strong performance because dent defects create distinguishable shapes and textures.

---

## Weakest Performing Class

The `scratch` class achieved lower performance.

Possible reasons:
- Scratch patterns are thin and difficult to detect.
- Scratch defects may appear visually similar to normal surfaces.
- Small dataset size limits feature learning.

---

# Generated Outputs

The following outputs were generated successfully:

1. Accuracy and Loss Curves
2. Confusion Matrix
3. Sample Prediction Images
4. Trained CNN Model

---

# Task 6: CNN Concept Explanation

## What is Convolution?

Convolution is a mathematical operation where filters scan images to detect important visual patterns such as:
- edges
- textures
- shapes
- object features

CNN models automatically learn these features during training.

---

## Why is Pooling Used?

Pooling reduces image dimensions while preserving important features.

### Benefits:
- Reduces computational cost
- Speeds up training
- Reduces overfitting
- Keeps important visual information

---

## Why is ReLU Commonly Used in CNNs?

ReLU (Rectified Linear Unit) introduces non-linearity into neural networks.

### Formula

```python
f(x) = max(0, x)
```

### Advantages
- Faster training
- Solves vanishing gradient problem
- Improves deep learning performance

---

## Why are CNNs Better than Regular Feed-Forward Networks for Image Data?

CNNs are better because:
- They preserve spatial relationships in images
- They automatically learn features
- They require fewer parameters
- They perform efficiently on image data

Regular feed-forward networks cannot effectively capture image patterns.

---

# Task 7: Business Use Case Mapping

## Manufacturing Quality Inspection

This CNN-based computer vision solution can be used in manufacturing industries for automatic defect detection and product quality inspection.

---

## Real-World Benefits

- Faster inspection process
- Reduced manual effort
- Improved product quality
- Reduced operational costs
- Real-time defect detection

---

## Example Use Case

Factories can install cameras on production lines to automatically identify:
- scratches
- dents
- stains

on products before packaging and shipment.

This helps improve manufacturing efficiency and product reliability.

---

# Technologies Used

- Python
- TensorFlow/Keras
- OpenCV
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

---

# Project Structure

```text
part-2-cnn-computer-vision/
│
├── README.md
├── notebook.ipynb
├── requirements.txt
├── cnn_defect_classifier.keras
│
├── results/
│   ├── accuracy_loss_curves.png
│   └── confusion_matrix.png
│
└── sample_predictions/
    └── prediction_outputs.png
```

---

# Conclusion

This project successfully demonstrates the implementation of a Convolutional Neural Network (CNN) for manufacturing defect classification using computer vision techniques.

The trained CNN model learned visual defect patterns from product surface images and achieved satisfactory classification performance.

The project also demonstrates:
- image preprocessing
- feature extraction
- CNN architecture design
- model training
- performance evaluation
- business application mapping

This type of computer vision system can be applied in real-world industrial quality inspection environments.

---
