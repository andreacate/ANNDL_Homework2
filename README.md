# Mars Terrain Segmentation

This repository contains the implementation of supervised image segmentation models for identifying Mars terrain types using deep learning techniques. The project focuses on segmenting grayscale images of size (64x128) into five classes: **Background**, **Soil**, **Bedrock**, **Sand**, and **Big Rock**.

## 📂 Dataset
- **Original Dataset**: 2615 grayscale labeled images from Mars terrain.
- **Cleaning**: Removed duplicates and corrected mislabeled images, creating refined datasets.
- **Balancing**: Enhanced the **"Big Rock"** class using manual cropping and data augmentation.
- **Augmentation**: Applied geometric transformations and the **Albumentations** library for dataset expansion.

## ⚙️ Loss Functions
- **Sparse Categorical Cross-Entropy (SCCE)** as a baseline.
- **Dice Loss** and **Focal Loss** to handle class imbalance and challenging classifications.
- Weighted loss functions to prioritize terrain classes over the **Background**.

## 🧠 Models
1. **Baseline U-Net**:
   - Simple encoder-decoder architecture.
   - Limited performance.
2. **DeepLab V3**:
   - Introduced **Atrous Spatial Pyramid Pooling (ASPP)** for multi-scale feature extraction.
3. **W-Net**:
   - Dual U-Net architecture for segmentation refinement.
   - Showed moderate improvements.
4. **Pyramid Scene Parsing Network (PSP-Net)**:
   - Captures global and local context using multi-scale pooling in the bottleneck.
   - Achieved significant performance gains when combined with attention mechanisms.
5. **Attention Gates**:
   - Improved focus on relevant regions by dynamically weighting features during upsampling.

## 🏆 Results
- The best performance was achieved using **PSP-Net** combined with attention gates and weighted loss functions.
- **Mean Intersection over Union (mIoU)** on the Kaggle test set: **71.78%**.

This project was completed as part of the **Artifial Neural Networks and Deep Learning (AN2DL)** course.
