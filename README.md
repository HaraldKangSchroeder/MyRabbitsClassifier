# MyRabbitsClassifier

This is a private project of mine. It is a classification model approach using machine learning to classify my own rabbits based on images. 
It also provides the dataset I used and on which I achieved an accuracy of ~95% based on a vgg16 and mobilenet model.

## My rabbits!
<img src="https://user-images.githubusercontent.com/81776044/144905043-f42664dd-72c5-4714-ae68-1c28754ac5fa.jpg" width="200" height="150" /> <img src="https://user-images.githubusercontent.com/81776044/144903724-cfc24a34-c99c-40b7-824f-411424036e9e.jpg" width="200" height="150" /> <img src="https://user-images.githubusercontent.com/81776044/144903834-f2c2cb28-0e00-4161-9c9a-dfef5bb69f16.jpg" width="200" height="150" /> <img src="https://user-images.githubusercontent.com/81776044/144904102-cdca359f-cd41-4dd5-95aa-a6f74e3025d8.jpg" width="200" height="150" />

## Setup
This section describes how you can replicate my results. I based my implementation on the following video (https://www.youtube.com/watch?v=qFJeN9V1ZsI) which I can highly recommend if you want to get in touch with Keras.
### Datasets
I have prepared 2 Datasets. https://drive.google.com/file/d/1_PauLuJM0xXEXIgIDNmxy0ubBBeTlQaF/view?usp=sharing contains raw data of around 100 images of each class (/each rabbit) without data preprocessing and preparation for the training,
https://drive.google.com/file/d/1zpP-sY6fBMra5fFDfAqVPDOOo2MRCB9u/view?usp=sharing contains data prepared for training.

### Preprocessing and preparation
Download the respective zip.file, extract it and place the data folder inside the project root directory. By executing each cell in the notebook file `data_preprocessor.ipynb`, you
1. apply an augmentation step by rotating, shifting ... the raw images to increase the number of training samples. Right now, each image is duplicated+augmented 10 times. However,
you can play around with my settings and change the augmentation parameters as desired. You will find the augmented images in `/data/augmented/<CLASS>` for each class. This took almost 4 hours in my case.

2. prepare the data by splitting them into a training, test and validation set. By default, the training set will have 900 images per class, the validation set 100 and the test set 30 which you can find in `/data/<validation || test || training>`.

### Training
If you want to skip the preprocessing, you can directly start training with my preprocessed data.
Download the respective zip.file, extract it and place the data folder inside the project root directory. You can then either use the `mobilenet_training.ipynb` or the `vgg16_training.ipynb` to adapt parameters and train the model. Afterwards, a confusion matrix will plot the performance of the model. 
