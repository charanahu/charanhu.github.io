---
title: "Emotion Finder using Convolutional Neural Network"
description: "A computer vision project about emotion detection"
dateString: Sept 2022 - Sept 2022
draft: false
tags: ["Python", "PyTorch", "CNN", "ML", "DL", "AI", "Machine Learning"]
showToc: false
weight: 198
cover:
    image: "https://miro.medium.com/max/1400/1*pW1RdOSF70xbmGuFeYqt6A.png"
--- 
### 🔗[Colab Notebook](https://colab.research.google.com/github/charanhu/Emotion-Finder-using-Convolutional-Neural-Network/blob/main/FaceEmotionDetectorCaseStudy.ipynb)

## Description
Describing an image is the problem of generating a human-readable textual description of an image, such as a photograph of an object or scene. It combines both computer vision and natural language processing together.

### Dataset:
The dataset which we’ll use is fer2013 which was published in International Conference on Machine Learning in 2013.

OpenCV-Python is a library of Python bindings designed to solve computer vision problems.cv2.imread() method loads an image from the specified file. If the image cannot be read (because of the missing file, improper permissions, unsupported or invalid format) then this method returns an empty matrix.

   Three main steps:
   1. face detection,
   2. features extraction
   3. emotion classification.

![Model Architecture](https://www.researchgate.net/profile/Rajesh-K-M/publication/317915825/figure/fig2/AS:961693140131844@1606296920490/Block-diagram-of-Emotion-detection-system-Here-input-images-are-classified-into-two.ppm)

The dataset used can be downloaded using the following links.

https://www.kaggle.com/datasets/msambare/fer2013

### Face Emotion Recognition using Transfer Learning

Transfer learning is applying knowledge from one field to another, us humans are really good at transfer learning, for example if we learn something we can easily transfer that knowledge and apply it somewhere else. Now we want to apply the same thing for neural networks, we can take weights from already pretrained models on huge datasets and fine-tune them to do our task.

This works because those pretrained weights can detect features that are very useful for our task especially when don’t have a lot of data. To do this you can use models such as MobileNet, VGG, Inception, ResNet, EfficientNet all of these models are trained on the ImageNet dataset which is a very huge dataset. We will not discuss their architectures but I urge you to check their research papers to get a clear and full understanding.

### Conclusion
There’s still a lot to be done on this project for example we can get more data or try LSTM + CNN models, also there are research papers who tackle this task so we can check them and try to implement them. 


