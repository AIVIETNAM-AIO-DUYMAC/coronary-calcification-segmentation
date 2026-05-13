# Automated Preprocessing Pipeline for Coronary Artery Calcium (CAC) Scoring

This repository provides a Python-based pipeline designed to transform raw medical imaging data (**DICOM**) and clinician annotations (**XML**) from the **Stanford COCA Dataset** into a deep learning-ready format (**2.5D NumPy arrays**).

## 🌟 Key Features
- **Hounsfield Unit (HU) Conversion**: Automatically rescales raw pixel values to standardized HU for medical consistency.
- **Dynamic Windowing**: Optimized range of **[-100, 500] HU** to enhance visibility of bone and calcification.
- **2.5D Spatial Stacking**: Generates 3-channel image tensors (Previous, Current, Next slice) to provide critical spatial context for neural networks.
- **Automated Batch Processing**: Efficiently handles large patient cohorts with built-in support for resuming interrupted tasks.
- **Anatomical Alignment**: Ensures precise Z-axis sorting to perfectly synchronize image slices with their respective XML labels.

## 📁 Project Structure
```text
CAC-Scoring-Project/
│
├── pipeline.py          # Core logic (HU conversion, XML parsing, 2.5D stacking)
├── preprocess.py        # Automation script for batch processing across the dataset
├── requirements.txt     # List of necessary Python dependencies
├── .gitignore           # Prevents large medical data (.dcm, .npy) from being uploaded
└── README.md            # Project documentation
