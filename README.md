# Petals-to-the-Metal_Flower_Classification.
Flower classification using Tensor Processing Unit(TPU) in Colab enviroment


# Petals to the Metal: Flower Classification

![Flower Classification](https://storage.googleapis.com/download.tensorflow.org/example_images/flower_photos.tgz)  
*A TensorFlow-based project for classifying flowers into five categories: Daisy, Roses, Dandelion, Tulips, and Sunflowers.*

## Overview

This project demonstrates how to build a flower classification model using TensorFlow and transfer learning with ResNet50. The dataset consists of 3,670 images across five flower categories. The model is trained on Google Colab with optional TPU acceleration for improved performance.

---

## ⚠️ Important Note  
This script (`petals_to_the_metal_flower_classification.py`) was developed and tested in **Google Colab**. If running locally, you may encounter differences due to:  
- **TPU/GPU dependencies**: Remove TPU-specific code if no accelerator is available.  
- **File paths**: Adjust paths (e.g., `/content/...`) to match your local environment.  
- **Google Drive mounting**: Replace `drive.mount()` with local dataset paths.  

---

## Features

- **Dataset**: Uses the [Flower Photos dataset](https://storage.googleapis.com/download.tensorflow.org/example_images/flower_photos.tgz) from TensorFlow.
- **Preprocessing**: Converts JPEG images to TFRecords for efficient training.
- **Model**: Transfer learning with ResNet50 as the base model.
- **Training**: Supports TPU/GPU acceleration and includes data augmentation.
- **Evaluation**: Metrics include sparse categorical accuracy and loss.

## Dataset Structure

The dataset contains the following flower categories:
- Daisy
- Dandelion
- Roses
- Sunflowers
- Tulips

## Requirements

- TensorFlow 2.x
- Google Colab (for TPU/GPU support)
- Python 3.7+
- Libraries: NumPy, Pandas, Matplotlib, scikit-learn

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/Petals to the Metal_Flower_Classification.git
   cd Petals to the Metal_Flower_Classification

2. Install dependencies:
   ```bash
   pip install tensorflow numpy pandas matplotlib scikit-learn
3. Download the dataset:
   - The dataset is automatically downloaded in the notebook from TensorFlow Datasets.

## Usage
##A. Google Colab
- Upload the .py file to Colab.

- Replace !cp /content/drive/MyDrive/... with your dataset path.

- Run all cells (skip TPU setup if unused).

  --------------
1. Open the notebook in Google Colab or Jupyter:
   ```bash
   jupyter notebook Petals_to_the_Metal_Flower_Classification.ipynb
2. Run the cells sequentially to:

- Load and preprocess the dataset.

- Convert images to TFRecords.

- Train the model using ResNet50.

- Evaluate the model on test data.

## Training
The model is trained with the following configuration:

- Batch size: 16 (scaled by replicas if using TPU)

- Image size: 512x512 (resized to 256x256 for training)

- Epochs: 25

- Optimizer: Adam with exponential decay learning rate

## Results
The model achieves the following metrics:

- Training accuracy: ~95%

- Validation accuracy: ~90%

## License
This project is licensed under the MIT License. See the LICENSE file for details.

## Acknowledgments
- Dataset provided by TensorFlow.

- Model architecture inspired by ResNet50.

- TPU support via Google Colab.

