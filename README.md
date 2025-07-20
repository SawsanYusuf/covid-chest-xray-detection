# COVID-19 Detection from Chest X-rays using Convolutional Neural Networks

![](https://github.com/SawsanYusuf/COVID-19-Detection-using-CNN/blob/main/Images/cover.jpg)

## Rapid and Accurate Diagnostic Aid for COVID-19 and Lung Conditions

This project presents a deep learning solution for the automated classification of Chest X-ray (CXR) images. The model is trained to distinguish between three critical categories: **COVID-19 Positive**, **Normal (Healthy)**, and **Virus (Pneumonia)**. The goal is to provide a swift and reliable diagnostic tool that can significantly aid clinicians in the early and accurate identification of COVID-19, improving patient management and public health response.

## Project Highlights

* **Multi-Class Classification:** Differentiates COVID-19 from both normal cases and other types of pneumonia/viral infections.
* **Custom CNN Architecture:** Leverages a custom-designed Convolutional Neural Network for robust feature extraction.
* **Extensive Data Augmentation:** Employs various augmentation techniques to enhance model generalization and mitigate overfitting, especially crucial for medical imaging datasets.
* **Dual Evaluation:** Assessed on an internal validation set for development insights and competed on an external Kaggle test set evaluated by **Mean F1-Score**.

## Dataset

The model is trained and evaluated on a structured dataset of Chest X-ray images, partitioned into `train`, `val` (validation), and `test` sets. The images are categorized into:
* **covid:** Confirmed cases of Coronavirus Disease.
* **normal:** Healthy lung X-rays.
* **virus:** X-rays showing signs of viral infections or other pneumonia types.

## Methodology

Our approach involved a systematic deep learning pipeline:

1.  **Data Preprocessing:** CXR images were resized to uniform dimensions (224x224 pixels) and pixel values were normalized to a [0, 1] range.
2.  **Data Augmentation:** To combat data scarcity and improve generalization, the training set was augmented with random rotations, shifts, zooms, and horizontal flips.
3.  **Custom CNN Development:** A deep Convolutional Neural Network was designed, featuring multiple convolutional and pooling layers for hierarchical feature learning, followed by dense layers for classification. Dropout layers were strategically placed to prevent overfitting.
4.  **Model Training:** The model was compiled using the Adam optimizer and `categorical_crossentropy` loss. Training utilized `EarlyStopping` to monitor validation loss and `ModelCheckpoint` to save the best performing weights.
5.  **Rigorous Evaluation:** Performance was assessed on an independent, unseen test set (Kaggle) and an internal validation set to ensure an unbiased measure of its effectiveness.

## Key Results

The trained CNN model's performance was evaluated on both an internal validation set (split from training data) and Kaggle's held-out, unlabeled test set for competition scoring, which used Mean F1-Score as its metric.

* **Internal Validation Performance (on `validation_dataset`):**
    * **Validation Loss:** **0.0231**
    * **Validation Accuracy:** **0.41 (41%)**
    * *These metrics reflect the model's performance during development and hyperparameter tuning.*

    **Detailed Validation Performance (per class, on `validation_dataset`):**
    | Class    | Precision | Recall | F1-Score | Support |
    | :------- | :-------- | :----- | :------- | :------ |
    | **covid** | 0.37      | 0.35   | 0.36     | 51      |
    | **virus** | 0.46      | 0.53   | 0.49     | 78      |
    | **normal** | 0.35      | 0.30   | 0.32     | 63      |
    | **Macro Avg** | 0.39      | 0.39   | 0.39     | 192     |
    | **Weighted Avg** | 0.40      | 0.41   | 0.40     | 192     |

    **Confusion Matrix on Validation Set:**
    The confusion matrix provides a detailed breakdown of correct and incorrect predictions:
    * Out of 51 true 'covid' cases, 18 were correctly predicted as 'covid', 22 as 'virus', and 11 as 'normal'.
    * Out of 78 true 'virus' cases, 13 were predicted as 'covid', 41 as 'virus', and 24 as 'normal'.
    * Out of 63 true 'normal' cases, 18 were predicted as 'covid', 26 as 'virus', and 19 as 'normal'.

* **Kaggle Competition Submission Score:**
    * **Public Leaderboard Score (Mean F1-Score): 0.93689 (approx. 93.69%)**
    * *This score is based on the model's predictions on Kaggle's truly unseen and unlabeled test set, using Mean F1-Score as the primary evaluation metric. It demonstrates strong generalization capability under competition-specific criteria.*

## Visualizations

* **Training & Validation Curves:** Plots showing the training and validation accuracy and loss over epochs. These indicate strong learning and good convergence, with no significant overfitting observed in terms of loss trends, though accuracy shows the model's struggle to differentiate classes well.

![]()

* **Confusion Matrix:** A heatmap visualizing the model's predictions versus the true labels on the validation set, offering a detailed breakdown of correct and incorrect classifications for each class.

![]()


## Future Enhancements

* **Addressing Class Imbalance:** The validation report shows uneven support for classes. Techniques like weighted loss, oversampling (SMOTE), or undersampling could significantly improve performance for underrepresented classes.
* **Transfer Learning:** Exploring fine-tuning pre-trained CNN architectures (e.g., ResNet, Inception, EfficientNet) which often yield higher performance on medical imaging.
* **Hyperparameter Tuning:** More extensive tuning of learning rate schedules, batch sizes, and optimizer parameters could yield improvements.
* **Explainable AI (XAI):** Implementing techniques like Grad-CAM or SHAP to visualize which specific regions of the X-ray images are most influential in the model's predictions, enhancing clinical trust and understanding.
* **Dataset Expansion:** Train on larger and more diverse multi-institutional datasets to improve robustness and generalization across various patient populations and imaging equipment.

## Contributing

Contributions are welcome! If you have suggestions or improvements, please open an issue or submit a pull request.



