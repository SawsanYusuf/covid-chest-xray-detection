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


## 3. Data Loading & Image pre-processing

In this step, we loaded the data and performed pre-processing of chest x-ray images so that model can understand the pattern hidden in the image for a particular class.

After loading the images, we reside the images to a uniform size of 224x224 pixels. We then assigned label values
of 0, 1, and 2 to the classes Normal, COVID-19, and Virus Infection, respectively. 

Next, we randomized the order so that they were not sorted according to any
specific pattern during the training of
our CNN model. This helps to prevent
any bias towards a particular order and
improves the overall performance of
the model.

Finally, we split our training data into training and validation sets with an 80:20 ratio. We used 80% of the data for training and the remaining 20% for evaluating the model.

## 4. Image Normalization and Augmentation

In this step, we normalized the given data by dividing it by 255. This was done to ensure that the data falls within the range of 0 to 1.

Then, we have implemented image augmentation to enhance the training data and build a more reliable model. Image augmentation is a technique in which we apply various transformations
to the training images, resulting in the
introduction of some noise that helps in
creating a robust model. 

For this project, we have utilized three transformations, namely share range, zoom range, and horizontal flip. 

## 5. Model Building 

Convolutional Neural Networks come in many different variants, this is our CNN architecture for solving our task.
![]()

This architecture is a traditional Feed Forward Network trained via back-propagation. In the context of this image, Feed Forward means that incoming data flows downwards through the layers. During training, weights in each layer (including Convolutional Filters) are updated from the bottom up, using back-propagation.





