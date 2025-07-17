# Water Segmentation with U-Net using Multispectral Data

![Python](https://img.shields.io/badge/Python-3.10+-blue?style=for-the-badge&logo=python)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.15+-orange?style=for-the-badge&logo=tensorflow)

This repository contains a deep learning solution for accurately segmenting water bodies from 12-channel multispectral satellite data. The project uses a U-Net architecture implemented in TensorFlow/Keras. This work was completed as part of a project for **Cellula Technologies**.

## Project Objective
The goal is to develop a robust solution vital for monitoring water resources, flood management, and environmental conservation, where precise segmentation of water bodies can significantly impact decision-making.

---

## 📊 Performance Summary

The model was trained for 25 epochs, with `EarlyStopping` and `ModelCheckpoint` callbacks monitoring the validation IoU. The best weights were restored from **Epoch 22**, which achieved the highest validation IoU. The final performance metrics from this epoch are summarized below:

| Metric             | Training Set | Validation Set |
| ------------------ | ------------ | -------------- |
| **IoU**            | 0.789        | **0.756**      |
| **Loss**           | 0.179        | 0.207          |
| **Accuracy**       | 0.935        | 0.938          |
| **Precision**      | 0.905        | 0.859          |
| **Recall**         | 0.860        | 0.863          |

---

## 🖼️ Prediction Samples

Below are examples of the model's performance on images from the validation set, comparing the original image, the ground truth mask, and the model's predicted output.

<table align="center">
  <tr>
    <td align="center"><b>Sample 1</b></td>
    <td align="center"><b>Sample 2</b></td>
  </tr>
  <tr>
    <td><img src="results/Predicted_sample_1.png" width="450"></td>
    <td><img src="results/Predicted_sample_2.png" width="450"></td>
  </tr>
</table>

---

## 📈 Training History

The training progress over the full 25 epochs demonstrates effective learning and the importance of early stopping to prevent overfitting.

<table align="center">
  <tr>
    <td align="center"><b>Loss</b></td>
    <td align="center"><b>Accuracy</b></td>
  </tr>
  <tr>
    <td><img src="results/Training_and_validation_loss.png" width="400"></td>
    <td><img src="results/Training_and_validation_accuaracy.png" width="400"></td>
  </tr>
  <tr>
    <td colspan="2" align="center"><b>Intersection-over-Union (IoU)</b></td>
  </tr>
  <tr>
    <td colspan="2" align="center"><img src="results/Training_and_validation_IoU.png" width="400"></td>
  </tr>
</table>

---
## 📚 Dataset

The model was trained on a custom "Water Segmentation Multispectral Dataset". This dataset consists of 12-channel multispectral satellite images, each with a resolution of 128x128 pixels. Each `.tif` image is paired with a corresponding binary segmentation mask (`.png`) that precisely identifies water bodies.

### Data Integrity and Cleaning

A crucial step in this project was addressing data inconsistencies. Upon initial inspection, the dataset contained a mismatch between the number of images and their corresponding labels:

-   **Initial Images:** 306 files
-   **Initial Masks:** 456 files

To resolve this, a data cleaning function was implemented within the `Water_Segmentation_using_Multispectral_and_optical_Data.ipynb` script. This function programmatically identifies and retains only the image-mask pairs with matching base filenames, deleting any orphaned files. This preprocessing step resulted in a clean, synchronized dataset of **306 pairs**, ensuring data integrity for the training pipeline.

### Training and Validation Splits

The cleaned dataset of 306 image-mask pairs was split into training and validation sets using an 80/20 ratio:

-   **Training Set**: 245 images (80%)
-   **Validation Set**: 61 images (20%)

### How to Get the Data

You can download it directly from the link below.

**[Download Water Segmentation Dataset from Google Drive](https://drive.google.com/drive/folders/1GQss5oZhv-0dxoRtI5m_m_SPbm-E3vXJ)**


---

## 🚀 Setup and Installation

To get this project up and running locally, follow these steps:

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/MohanadMetrash/Water-Segmentation-UNET.git
    cd Water-Segmentation-UNET
    ```

2.  **Create a virtual environment (recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3.  **Install the required dependencies:**
    ```bash
    pip install -r requirements.txt
    ```



