---
title: "Skin Cancer Detection using CNN(Convolutional Neural Network)"
description: "Can computers detect the cancer of an image?"
dateString: Jan 2021 - May 2021
draft: false
tags: ["Python", "PyTorch", "CNN", "ML", "DL", "AI"]
showToc: false
weight: 203
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
![Model Architecture](https://github.com/charanhu/Skin_Cancer_Detection_MNIST/blob/main/model_architecture.png?raw=true)

Furthermore, beam search is used during inference to enhance the prediction result. The network was trained in **PyTorch** on an **Nvidia GTX 1060** graphics card for over 80 epochs.

Model is deployed on heroku cloud. 
#### 🔗[Click here to Upload a sample skin image to see the result](https://skin-cancer-detection-cnn.herokuapp.com/)