# DermaScan AI - Skin Disease Classification using Deep Learning

## Overview

DermaScan AI is a deep learning-based skin disease classification system developed using the HAM10000 dataset. The project uses transfer learning with MobileNetV2 to classify dermoscopic skin lesion images into multiple disease categories.

The goal is to assist in the early identification of common skin conditions by analyzing lesion images and predicting the most likely disease category.

---

## Features

* Skin lesion image classification
* Transfer Learning using MobileNetV2
* Image preprocessing and augmentation
* Multi-class disease prediction
* Disease information and guidance system
* Model evaluation and performance analysis

---

## Dataset

Dataset Used: HAM10000 (Human Against Machine with 10000 Training Images)

The dataset contains dermoscopic images belonging to seven different skin disease classes:

| Code  | Disease                                         |
| ----- | ----------------------------------------------- |
| akiec | Actinic Keratoses and Intraepithelial Carcinoma |
| bcc   | Basal Cell Carcinoma                            |
| bkl   | Benign Keratosis-like Lesions                   |
| df    | Dermatofibroma                                  |
| mel   | Melanoma                                        |
| nv    | Melanocytic Nevi                                |
| vasc  | Vascular Lesions                                |

Dataset Source:
https://www.kaggle.com/datasets/kmader/skin-cancer-mnist-ham10000

---

## Technologies Used

* Python
* TensorFlow / Keras
* MobileNetV2
* OpenCV
* NumPy
* Pandas
* Matplotlib
* Scikit-Learn

---

## Model Architecture

* Base Model: MobileNetV2 (Pretrained on ImageNet)
* Global Average Pooling Layer
* Dropout Layer (0.3)
* Dense Output Layer (7 Classes)
* Softmax Activation

Transfer learning was used by freezing the MobileNetV2 base layers and training a custom classification head.

---

## Data Processing

1. Load HAM10000 metadata
2. Map image paths
3. Encode disease labels
4. Train-test split with stratification
5. Image augmentation:

   * Rotation
   * Zoom
   * Horizontal Flip
6. Resize images to 224 × 224

---

## Training Configuration

* Optimizer: Adam
* Loss Function: Categorical Crossentropy
* Epochs: 5
* Batch Size: 32

---

## Results

Test Accuracy: 73.79%

The model demonstrates effective classification performance using transfer learning on the HAM10000 dataset.

---

## Project Structure

DERMASCAN-AI/

├── Notebooks/

│ └── dermascanai.ipynb

├── Models/

│ └── skin_model.keras

├── Datasets/

│ ├── HAM10000_metadata.csv

│ ├── HAM10000_images_part_1/

│ └── HAM10000_images_part_2/

├── Uploads/

└── README.md

---

## Future Improvements

* Increase training epochs
* Fine-tune MobileNetV2 layers
* Build a Flask or Django web application
* Deploy using Streamlit
* Improve classification accuracy
* Add real-time skin lesion analysis

---

## Disclaimer

This project is intended for educational and research purposes only. It is not a substitute for professional medical diagnosis. Always consult a qualified dermatologist for medical advice.

---

## Testing a New Skin Image

After training the model and loading the saved model:

1. Place the image inside the `Uploads` folder.
2. Update the image path in the notebook.
3. Run the prediction cell.

### Example

```python
test_image = "../Uploads/images.jpeg"

analyze_user_skin_image(
    test_image,
    trained_model
)
```

### Output

The system generates a detailed report including:

* Predicted Skin Disease
* Confidence Score
* Severity Risk Level
* Disease Description
* Recommended Action

Example:

```text
DERMASCAN AI DETECTION REPORT

AI Prediction      : Melanocytic Nevi
Confidence Score   : 95.42%
Severity Risk Level: Benign
```


## Author

Liyona Moncy

Computer Science Student | AI & Machine Learning Enthusiast

