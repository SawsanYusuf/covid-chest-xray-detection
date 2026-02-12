# COVID-19 Detection from Chest X-rays using CNN

![COVID-19 Detection](https://img.shields.io/badge/Status-Complete-green)
![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange)
![Kaggle Score](https://img.shields.io/badge/Kaggle_Score-0.936-blueviolet)

## 1. Project Overview
This project details the development of a deep learning model to classify Chest X-ray (CXR) images into three categories: **COVID-19 Positive**, **Normal (Healthy)**, and **Viral Pneumonia**. The objective is to provide a rapid, automated diagnostic aid to differentiate these conditions, supporting clinical decision-making during high-traffic screening.

## 2. Dataset Description
The dataset consists of Chest X-ray images structured into training, validation, and test directories.
* **COVID-19**: X-rays of patients diagnosed with COVID-19.
* **Normal**: X-rays of healthy individuals.
* **Viral Pneumonia**: X-rays of patients with other viral lung infections are vital for differential diagnosis.

**Data Summary:**
* **Total Training Samples**: 1,196 images.
* **Image Dimensions**: $224 \times 224$ pixels (RGB).
* **Distribution**: 468 Normal, 186 Virus, and 128 COVID-19 samples.

## 3. Model Architecture
The architecture utilizes a modular VGG-style Convolutional Neural Network (CNN) built with `TensorFlow/Keras`.

* **Input Layer**: Accepts $224 \times 224 \times 3$ images.
* **Convolutional Blocks**: Sequential $3 \times 3$ filters with `padding='same'` to preserve spatial dimensions and `ReLU` activation.
* **Downsampling**: MaxPooling layers ($2 \times 2$) follow each block.
* **Regularization**: Dropout layers ($0.3$) are strategically placed to prevent overfitting.
* **Classification Head**: Flatten layer followed by two Dense layers ($512$ units) and a final 3-unit Softmax output.

## 4. Technical Stack
* **Language**: Python 3
* **Core Libraries**: TensorFlow, Keras, NumPy, Pandas.
* **Metrics & Evaluation**: Scikit-learn (Classification Report, Confusion Matrix).
* **Visualization**: Matplotlib, Seaborn.

## 5. Model Performance
The evaluation reveals a nuanced performance profile between internal validation and external testing.

### 5.1 Internal Validation (41% Accuracy)
On the internal validation set, the model achieved an accuracy of **41%**, highlighting significant challenges in fine-grained differentiation:
* **COVID-19 Class**: F1-score of **0.36** with a recall of **0.35**, indicating a high rate of false negatives.
* **Virus Class**: Strongest performance with an F1-score of **0.49** and **53% recall**.
* **Normal Class**: Low recall of **0.30**, suggesting difficulty in delineating healthy features from disease.

### 5.2 Kaggle Performance (93.69% Mean F1-Score)
Despite internal validation struggles, the model achieved a **Kaggle Public Leaderboard Score of 0.93689**. This high Mean F1-Score suggests that the model generalizes well to external test data and produces well-calibrated probability outputs that excel under F1-based evaluation metrics.

## 6. Future Scope
* **Multi-Modal Learning**: Integrating clinical data (symptoms, age) with radiological images for improved accuracy.

* **Deployment**: Building a web interface using Flask/FastAPI for real-time clinical use.

* **Explainable AI (XAI)**: Using Grad-CAM to generate heatmaps so clinicians can see exactly where the model detects abnormalities.

* **Dataset Expansion**: Incorporating more diverse datasets to reduce demographic bias in predictions.

## 7. Conclusion
The model demonstrates high potential for real-world utility, as evidenced by its strong performance on external data (Kaggle). While the internal validation highlights the inherent difficulty in distinguishing between COVID-19 and other viral pneumonias, the high F1-score confirms the model's ability to provide a robust "second opinion." Future refinements in class balancing and architecture will be essential for clinical-grade reliability.

   
## Author
**Sawsan Yousef** 

*Data Scientist | Predictive Modeling | Computer Vision*

[LinkedIn](https://www.linkedin.com/in/sawsan-yusuf-027b2b214?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app) | [Medium](https://medium.com/@sawsanyusuf)

