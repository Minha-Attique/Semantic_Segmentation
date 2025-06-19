# Semantic Segmentation using VGG16-UNet

This project implements a semantic segmentation pipeline using a VGG16 encoder with a UNet-style decoder. The goal is to accurately segment glacier imagery into multiple classes such as glacier ice, vegetation, water, and man-made structures.

## Objective
To segment satellite or aerial images into meaningful classes using deep learning, improving understanding of glacial environments and aiding in disaster risk analysis (e.g., GLOFs).

## Key Features
- VGG16-UNet architecture for multi-class semantic segmentation.
- Training on Passu and Shisper glacier datasets (2019–2023).
- Performance improvements through iterative experimentation.
- Class-level segmentation accuracy and Mean IoU tracking.

## Experiments & Results

### Small Dataset (12 Images)
- **Accuracy:** ~60%  
- **Issue:** Severe overfitting due to limited data.

### Handling Session Crashes
- Resolved memory crashes by reducing patch size, batch size, and loading data efficiently.

### Improved Data Loading
- Used data loaders and removed noisy augmentations.  
- Accuracy improved to ~85%.

### Final Notebook (`VGG16_UNET_BEST`)
- Batch size: 4 | Patch size: 128x128 | Epochs: 1000  
- **Training Accuracy:** 91.15%  
- **Validation Accuracy:** 90.12%  
- **Validation Mean IoU:** 63.07%

## Challenges & Solutions

### Solved
- Session crashes due to GPU overload
- Noisy augmentations
- Small batch size handling

### In Progress
- Class imbalance (8-class segmentation with underrepresented categories)
- Expanding dataset for better generalization
- Exploring loss functions like Dice and Focal Loss

## Lessons Learned
- Optimized prompts for ChatGPT to debug model behavior and tune hyperparameters.
- Developed a deep understanding of data handling, loss metrics, and training dynamics for semantic segmentation.

## Tech Stack
- Python, TensorFlow/Keras
- Google Colab (GPU)
- NumPy, OpenCV, Matplotlib

## Future Work
- Integrate focal loss to mitigate class imbalance.
- Support for high-resolution PPM datasets.
- Deploy segmentation app using Flask/Gradio (in progress).

## Notebooks Overview
- `Small_Dataset.ipynb` – Baseline results with limited data
- `Session_Crashes.ipynb` – Debugging and memory handling
- `IntroduceDataLoaders.ipynb` – Efficient data loading
- `VGG16_UNET_BEST.ipynb` – Final model with best performance

## New Improvements

- Added a new training script using **ResNet50 as encoder** with fine-tuning.
- Implemented **class weighting** to address class imbalance across 8 segmentation classes.
- Achieved **91% validation accuracy** and improved per-class performance using weighted loss functions.
---

## Author
**Minha Rehman**  
Final-year Computer Science student, FAST NUCES  
[LinkedIn](https://www.linkedin.com/in/minha-rehman-b67204250/) • minharehman45@gmail.com

