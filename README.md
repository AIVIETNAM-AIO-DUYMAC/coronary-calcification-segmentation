# Automated Preprocessing Pipeline for Coronary Artery Calcium (CAC) Scoring

This repository provides a Python-based pipeline designed to transform raw medical imaging data (**DICOM**) and clinician annotations (**XML**) from the **Stanford COCA Dataset** into a deep learning-ready format (**2.5D NumPy arrays**).

## 🌟 Key Features
- **Hounsfield Unit (HU) Conversion**: Automatically rescales raw pixel values to standardized HU.
- **Dynamic Windowing**: Optimized range of **[-100, 500] HU** to enhance visibility of bone and calcification.
- **2.5D Spatial Stacking**: Generates 3-channel image tensors (Previous, Current, Next slice).
- **Automated Batch Processing**: Efficiently handles large patient cohorts.

## 📁 Project Structure
```text
├── app                  # Pipeline Engineer (App logic)
├── data                 # Storage for raw and processed data
├── models               # Model Engineer (Architectures & Weights)
├── src                  # Core Source Code
│   ├── data_processing.py
│   ├── pre_processing.py
├── .gitignore
├── README.md
└── requirements.txt

## 📊 Data Output Details

The preprocessing pipeline automatically organizes the processed data into a structured format compatible with deep learning frameworks. By default, outputs are saved locally to the `/processed_npy/` directory.

### Output Structure:
- **Image Tensors:** `/processed_npy/images/` (Contains 2.5D NumPy arrays with shape `(K, 3, 512, 512)`).
- **Binary Masks:** `/processed_npy/masks/` (Contains corresponding segmentation masks).

### 🔗 Access Preprocessed Dataset
Due to the large file sizes, `.npy` files are excluded from this repository via `.gitignore`. You can access the full pre-processed dataset for training here:

> [**Download Processed Data from Google Drive**](https://drive.google.com/drive/folders/18Ka7Q3hTVjM2Zf0BZsQCM8fnXsPz982x?usp=sharing)
