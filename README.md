# COVID-19 Detection Using CNN

![](https://github.com/SawsanYusuf/COVID-19-Detection-using-CNN/blob/main/Images/cover.jpg)

## Introduction
In this project, we aimed to develop a Convolutional Neural Network (CNN) algorithm for the accurate detection of COVID-19 from Chest X-ray (CXR) images.

The challenge was to develop an algorithm that could accurately detect COVID-19, as well as distinguish between viral pneumonia, and normal cases based on an input chest X-ray image.

## 1. Dataset Description

In this project, we used the [COVID CXR Image Dataset](https://www.kaggle.com/competitions/copy-of-shai-level-2-training/data) which consists of a total of 1196 posteroanterior (PA) views of chest X-ray images comprising Normal, Viral, and COVID-19 affected patients.

The distribution of images in COVID-19, Viral, and Normal patients are shown in this plot.
![](https://github.com/SawsanYusuf/COVID-19-Detection-using-CNN/blob/main/Images/Distribution.png)

## 2. Exploratory Data Analysis
We plotted sample images of each class to understand the visual difference among different classes of images.

**Normal CXR Images**
![](https://github.com/SawsanYusuf/COVID-19-Detection-using-CNN/blob/main/Images/Normal.png)

**Viral Pneumonia CXR Images**
![](https://github.com/SawsanYusuf/COVID-19-Detection-using-CNN/blob/main/Images/Virus.png)

**Covid-19 CXR Images**
![](https://github.com/SawsanYusuf/COVID-19-Detection-using-CNN/blob/main/Images/COVID.png)

The sample images of COVID-19 CXR leave no doubt that normal CXR images depict clear lungs without any abnormal opacification patterns. It is important to note that viral pneumonia (middle) presents a more diffuse "interstitial"
pattern in both the left and right lungs, while COVID-19 CXR images clearly show ground-glass opacification and consolidation in the right upper lobe and left lower lobe.



