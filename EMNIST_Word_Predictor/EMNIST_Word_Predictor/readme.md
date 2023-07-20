# EMNIST_Word_Predictor

## Introduction

In this project, I have developed a computer vision model to predict single-line words containing up to 5 characters (letters or digits) using the EMNIST balanced dataset. The dataset consists of images of 47 characters, including 10 digits, 26 uppercase letters, and 11 lowercase letters. The goal is to predict the word in an image by first determining the number of characters present and then predicting the individual characters.

## Dataset Overview

The EMNIST balanced dataset contains character images with labels representing the decimal value of their ASCII codes. Each image is represented by 784 (28x28) pixel values, and the dataset includes 2400 training images for each character. Due to limited computational resources, a subset of the EMNIST dataset was used for this project.

**Please note that the complete dataset is not included in the repository due to its size. Instead, it can be downloaded from [Kaggle](https://www.kaggle.com/datasets/crawford/emnist) or [TensorFlow Datasets](https://www.tensorflow.org/datasets/catalog/emnist), as shown in the notebook.**

## Model Architecture

This project involves building two models:

1. Character Counter Model: This model predicts the number of characters present in a word image. It is a convolutional neural network (CNN) architecture inspired by a Kaggle published kernel. The model is compiled with the Adam optimizer and uses categorical cross-entropy loss. Remarkably, the character counter model achieves a validation accuracy of 100% in predicting the number of characters.

2. Word Predictor Model: The second step is to predict the individual characters in the word image based on the number of characters predicted in the previous step. For each number of characters (ranging from 1 to 5), a separate word predictor model is created. These models share a similar CNN architecture as the character counter model but are tailored to predict individual characters.

## Results and Conclusion

The word predictor models achieve an average individual character prediction accuracy of approximately 85.7%. However, as the number of characters in the word increases, the accuracy decreases. This is because the complexity of distinguishing similar characters compounds when predicting longer words.

Despite the challenges, the models perform well in predicting words from images. Some errors are observed due to the similarity between certain characters, such as "f" and "F," "l," "I," and "L," "U" and "V," "0" and "O," "q," "g," and "y," as well as "6" and "G." These similarities contribute to the model's relatively lower accuracy score of approximately 85.7%.

In conclusion, this project demonstrates the effectiveness of convolutional neural network models for character and word recognition using the EMNIST dataset. The models' performance could be further improved by exploring more sophisticated architectures and data augmentation techniques. Overall, this project showcases the potential of computer vision in solving real-world problems and provides valuable insights into character recognition tasks.