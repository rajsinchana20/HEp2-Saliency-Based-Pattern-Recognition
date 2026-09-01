# HEp-2 Saliency-Based Pattern Recognition

## A Deep Learning and Explainable AI Framework for Automated HEp-2 Cell Pattern Recognition

This project presents a deep learning and explainable AI framework for the automated classification of HEp-2 cell staining patterns. The system uses transfer learning models, including **ResNet50** and **DenseNet121**, to classify HEp-2 cell images. **Grad-CAM (Gradient-weighted Class Activation Mapping)** is used to visualize the image regions that influence the model's predictions.

---

## 📌 Project Motivation

HEp-2 cell pattern recognition is an important part of autoimmune disease analysis and typically requires visual interpretation of fluorescence images.

Manual interpretation can be:

- Time-consuming
- Subjective
- Dependent on expert knowledge
- Difficult to maintain consistently

Deep learning can assist in automatically recognizing HEp-2 staining patterns. However, deep learning models are often difficult to interpret.

This project combines automated pattern classification with explainable AI to improve transparency in the model's decision-making process.

---

## 🎯 Project Objectives

### Objective 1: HEp-2 Pattern Classification

Develop deep learning models for automated classification of HEp-2 cell staining patterns using:

- ResNet50
- DenseNet121

### Objective 2: Explainability Using Grad-CAM

Generate Grad-CAM saliency maps to visualize the image regions that contribute most strongly to the model's classification decisions.

### Objective 3: Model Comparison and Evaluation

Compare the trained models using classification performance metrics and analyze their performance on the HEp-2 test dataset.

---

## 🧬 Dataset

The dataset consists of HEp-2 cell images belonging to six staining-pattern classes.

### Classes

- Centromere
- Golgi
- Homogeneous
- NuMem
- Nucleolar
- Speckled

### Dataset Characteristics

| Feature | Description |
|---|---|
| Total Images | 13,596 |
| Number of Classes | 6 |
| Original Image Size | 78 × 78 pixels |
| Image Type | Grayscale |
| Pixel Intensity Range | 0–255 |

A class distribution analysis was performed during exploratory data analysis to identify potential class imbalance.

---

## 🔍 Exploratory Data Analysis

Exploratory Data Analysis (EDA) was performed to understand the characteristics of the HEp-2 dataset.

The following analyses were conducted:

- Class distribution analysis
- Visualization of representative images
- Image dimension analysis
- Pixel intensity distribution analysis

The EDA results were used to determine the preprocessing requirements before model training.

---

## ⚙️ Data Preprocessing

The following preprocessing steps were applied.

### Dataset Splitting

The dataset was divided using stratified sampling into:

- **70% Training Data**
- **15% Validation Data**
- **15% Testing Data**

Stratified splitting helps preserve the distribution of classes across the training, validation, and test datasets.

### Image Resizing

The original HEp-2 images were resized from **78 × 78 pixels** to:

**224 × 224 pixels**

This allows the images to be used with the CNN architectures.

### Channel Conversion

The original grayscale images were converted to three-channel images for compatibility with the CNN models.

### Data Augmentation

The following augmentation techniques were applied to the training dataset:

- Random Horizontal Flip
- Random Vertical Flip
- Random Rotation

Data augmentation was applied only to the training data.

### Image Normalization

Images were normalized using ImageNet mean and standard deviation values.

---

## 🤖 Deep Learning Models

### ResNet50

ResNet50 is a convolutional neural network architecture based on residual learning. Residual connections allow deep networks to learn complex image representations effectively.

### DenseNet121

DenseNet121 uses dense connections between layers, allowing feature reuse throughout the network.

Both models were trained for HEp-2 cell pattern classification.

---

## 📊 Current Model Performance

The trained models were evaluated on the test dataset.

| Model | Accuracy | F1-Score |
|---|---:|---:|
| ResNet50 | 96.96% | 96.97% |
| DenseNet121 | 97.55% | 97.54% |

Based on the current test performance, **DenseNet121 achieved slightly higher overall accuracy and F1-score**.

---

## 🔍 Explainable AI: Grad-CAM

Deep learning models can make accurate predictions, but understanding the regions that influenced a prediction is also important.

This project uses **Grad-CAM (Gradient-weighted Class Activation Mapping)** to generate visual explanations.

Grad-CAM:

1. Passes an image through the trained CNN model.
2. Identifies the target prediction.
3. Obtains gradients related to the target class.
4. Calculates the importance of feature maps.
5. Combines feature activations and gradient-based importance values.
6. Generates a saliency map.
7. Visualizes the important regions over the original image.

The highlighted regions represent areas that contributed strongly to the model's prediction. They should be interpreted as model-based explanations rather than standalone medical conclusions.

---

## 🏗️ System Workflow

```text
HEp-2 Dataset
      │
      ▼
Exploratory Data Analysis
      │
      ▼
Data Preprocessing
      │
      ├── Image Resizing
      ├── 3-Channel Conversion
      ├── Normalization
      └── Data Augmentation
      │
      ▼
Stratified Dataset Split
      │
      ├── Training Set (70%)
      ├── Validation Set (15%)
      └── Test Set (15%)
      │
      ▼
Deep Learning Classification
      │
      ├── ResNet50
      └── DenseNet121
      │
      ▼
HEp-2 Pattern Prediction
      │
      ▼
Grad-CAM Saliency Analysis
      │
      ▼
Visual Explanation
````

---

## 📂 Project Structure


HEp2-Saliency-Based-Pattern-Recognition/
│
├── 01_EDA_HEP2_Local.ipynb
├── 02_Preprocessing_HEp2_Local.ipynb
├── 03_ResNet50_HEp2_Local.ipynb
├── 04_DenseNet121_HEp2_Local.ipynb
├── 05_GradCAM_HEp2_Local.ipynb
├── 06_Model_Comparison_HEp2_Local.ipynb
├── 07_AI_Assisted_HEp2_Demo.ipynb
│
├── .gitignore
└── README.md


## 🛠️ Technologies Used

* Python
* PyTorch
* Torchvision
* NumPy
* Pandas
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook
* Git
* GitHub

---

## 📈 Evaluation Metrics

The models are evaluated using:

* Accuracy
* Precision
* Recall
* F1-Score
* Support
* Confusion Matrix

**Support** represents the number of actual samples belonging to a particular class in the evaluation dataset.

---

## 🚀 Implementation Progress

* [x] Dataset acquisition
* [x] Exploratory Data Analysis
* [x] Class distribution analysis
* [x] Representative image visualization
* [x] Image dimension analysis
* [x] Pixel intensity analysis
* [x] Data preprocessing
* [x] Stratified train, validation, and test split
* [x] Data augmentation
* [x] ResNet50 training
* [x] DenseNet121 training
* [x] Grad-CAM implementation
* [x] Model comparison
* [x] AI-assisted prediction demonstration
* [ ] Further validation and analysis
* [ ] Final project documentation

---

## 💡 Key Contribution

The key contribution of this project is the integration of:

> **Deep learning for automated HEp-2 pattern classification with Grad-CAM-based visual explanations for improved model interpretability.**

The system aims to provide both a classification result and an indication of the image regions that influenced the model's prediction.

---

## 🔮 Future Work

Possible future improvements include:

* Further validation using additional datasets
* Analysis of model performance across minority classes
* More detailed Grad-CAM analysis across HEp-2 patterns
* Investigation of misclassified samples
* Development of a user interface for image upload and automated analysis
* Further research into clinical validation and expert-assisted interpretation

---

## 📚 Academic Context

This project is developed as a final-year academic project in the areas of:

* Deep Learning
* Medical Image Analysis
* Computer Vision
* Explainable Artificial Intelligence

---

## ⚠️ Disclaimer

This project is intended for academic and research purposes. The developed system is an AI-assisted research prototype and is **not intended to replace professional medical diagnosis or expert laboratory interpretation**.

```


