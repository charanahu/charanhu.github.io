---
title: "Skin Cancer Detection using CNN(Convolutional Neural Network)"
description: "Can computers detect the cancer of an image?"
dateString: Jan 2021 - May 2021
draft: false
tags: ["Python", "PyTorch", "CNN", "ML", "DL", "AI", "Deep Learning", "Machine Learning"]
showToc: false
weight: 201
cover:
    image: "projects/skin-cancer-detection-cnn/skin-cancer-detection-cnn copy.jpeg"
--- 
### 🔗[Colab Notebook](https://colab.research.google.com/github/charanhu/Skin_Cancer_Detection_MNIST/blob/main/Skin_Cancer_Detection.ipynb)

## Description
In this project, The dataset consists of 10015 dermatoscopic images which
are released as a training set for academic machine learning
purposes and are publicly available through the ISIC archive. Here, I'm using RGB pixel values of that images(each image of
size 28*28, so total 784*3 pixel in each row). The objective to
build deep learning model to classify given query image into
one of the 7 different classes of skin cancer. 

### Model Architecture
![Model Architecture](https://github.com/charanhu/Skin_Cancer_Detection_MNIST/blob/main/model_architecture.png?raw=true)

Furthermore, beam search is used during inference to enhance the prediction result. The network was trained in **PyTorch** on an **Nvidia GTX 1060** graphics card for over 80 epochs.

Model is deployed on heroku cloud. 
#### 🔗[Click here to Upload a sample skin image to see the result](https://skin-cancer-detection-cnn.herokuapp.com/)

Build deep learning model to classify given query image into one of the 7 different classes of skin cancer.

Skin cancer is the most common human malignancy, is primarily diagnosed visually, beginning with an initial clinical screening and followed potentially by dermoscopic analysis, a biopsy and histopathological examination. Automated classification of skin lesions using images is a challenging task owing to the fine-grained variability in the appearance of skin lesions.

### Prerequisites:
This post assumes you are familiarity with basic knowledge of Data Preprocessing, Exploratory Data Analysis, Performance matric, Machine Learning, Deep Learning techniques like CNN, python syntax, some libraries like NumPy, Pandas, sk-learn, Matplotlib, Seaborn, PrettyTable, TensorFlow, Keras, etc.

### About Data:
#### Overview:
Another more interesting than digit classification dataset to use to get biology and medicine students more excited about machine learning and image processing.

#### Original Data Source:
Original Challenge: https://challenge2018.isic-archive.com
Training of neural networks for automated diagnosis of pigmented skin lesions is hampered by the small size and lack of diversity of available dataset of dermatoscopic images.
This the HAM10000 (“Human Against Machine with 10000 training images”) dataset. It consists of 10015 dermatoscopic images which are released as a training set for academic machine learning purposes and are publicly available through the ISIC archive. This benchmark dataset can be used for machine learning and for comparisons with human experts.
Cases include a representative collection of all important diagnostic categories in the realm of pigmented lesions: Actinic keratoses and intraepithelial carcinoma / Bowen’s disease (akiec), basal cell carcinoma (bcc), benign keratosis-like lesions (solar lentigines / seborrheic keratoses and lichen-planus like keratoses, bkl), dermatofibroma (df), melanoma (mel), melanocytic nevi (nv) and vascular lesions (angiomas, angiokeratomas, pyogenic granulomas and hemorrhage, vasc)
It has 7 different classes of skin cancer which are listed below:

1. Melanocytic nevi
2. Melanoma
3. Benign keratosis-like lesions
4. Basal cell carcinoma
5. Actinic keratoses
6. Vascular lesions
7. Dermatofibroma

### CNN Model
    model = Sequential()

    model.add(Conv2D(16, 
                 kernel_size = (3,3), 
                 input_shape = (28, 28, 3), 
                 activation = 'relu', 
                 padding = 'same'))

    model.add(MaxPool2D(pool_size = (2,2)))
    model.add(tf.keras.layers.BatchNormalization())

    model.add(Conv2D(32, 
                 kernel_size = (3,3), 
                 activation = 'relu'))

    model.add(Conv2D(64, 
                    kernel_size = (3,3), 
                    activation = 'relu'))

    model.add(MaxPool2D(pool_size = (2,2)))

    model.add(tf.keras.layers.BatchNormalization())

    model.add(Conv2D(128, 
                    kernel_size = (3,3), 
                    activation = 'relu'))

    model.add(Conv2D(256, 
                    kernel_size = (3,3), 
                    activation = 'relu'))

    model.add(Flatten())
    model.add(tf.keras.layers.Dropout(0.2))
    model.add(Dense(256,activation='relu'))

    model.add(tf.keras.layers.BatchNormalization())
    model.add(tf.keras.layers.Dropout(0.2))
    model.add(Dense(128,activation='relu'))

    model.add(tf.keras.layers.BatchNormalization())
    model.add(Dense(64,activation='relu'))

    model.add(tf.keras.layers.BatchNormalization())
    model.add(tf.keras.layers.Dropout(0.2))
    model.add(Dense(32,activation='relu'))

    model.add(tf.keras.layers.BatchNormalization())
    model.add(Dense(7,activation='softmax'))

    model.summary()

### Conclusion:
This model is not robust to all skin images, because, we not trained with good amount of equal class images data. Due to random oversampling it may give some wrong predictions to images.