# Water Segmentation with U-Net using Multispectral Data

![Python](https://img.shields.io/badge/Python-3.10+-blue?style=for-the-badge&logo=python)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.15+-orange?style=for-the-badge&logo=tensorflow)

This repository contains a deep learning solution for accurately segmenting water bodies from 12-channel multispectral and optical satellite data. The project uses a U-Net architecture implemented in TensorFlow/Keras. This work was completed as part of a project for **Cellula Technologies**.

## Project Objective
The goal is to develop a robust solution vital for monitoring water resources, flood management, and environmental conservation, where precise segmentation of water bodies can significantly impact decision-making.

---

## Results: Model Prediction
The model was trained for 25 epochs and achieved a **Validation Intersection-over-Union (IoU) of 0.756**. Below is a sample of the model's performance on images from the validation set.

*To add your image: take a screenshot of your 4-column output, drag-and-drop it into this text box on GitHub, and it will be uploaded and linked automatically!*

![Sample Predictions](link-to-your-screenshot-will-appear-here.png)

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

1.  **Download the Dataset:** You will need to acquire the `Water Segmentation.zip` dataset and place it in a relevant project directory. The script assumes a structure where the extracted data is located.

2.  **Update Paths:** Modify the paths inside `train.py` to point to your dataset location on your local machine or cloud environment.

3.  **Run the Training Script:**
    ```bash
    python train.py
    ```
    The script will perform data cleaning, build the U-Net model, train it, and save the best-performing model as `best_water_segmentation_model.keras`.

---

## 📂 File Structure

The repository is organized as follows:

```
├── .gitignore          # Specifies files for Git to ignore
├── README.md           # This overview file
├── requirements.txt    # Required Python packages
└── train.py            # Main script for data loading, preprocessing, training, and evaluation
```

---

## Acknowledgments
- Project provided by **Cellula Technologies**.
- Dataset consists of multispectral satellite imagery.
