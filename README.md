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

## 🚀 Setup and Installation

To get this project up and running locally, follow these steps:

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/your-username/water-segmentation-unet.git
    cd water-segmentation-unet
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

---

## ⚙️ Usage

1.  **Download the Dataset:** You will need to acquire the `Water Segmentation.zip` dataset and place it in a relevant project directory.

2.  **Update Paths:** Modify the paths inside `train.py` to point to your dataset location.

3.  **Run the Training Script:**
    ```bash
    python train.py
    ```
    The script will perform data cleaning, build the U-Net model, train it, and save the best-performing model as `best_water_segmentation_model.keras`.

---

## 📂 File Structure

```
├── .gitignore          # Specifies files for Git to ignore
├── README.md           # This overview file
├── requirements.txt    # Required Python packages
├── train.py            # Main script for all project stages
└── results/            # Contains output images and plots
```

---

## Acknowledgments
- Project provided by **Cellula Technologies**.
- Dataset consists of multispectral satellite imagery from a publicly available source.
