# Mpox
Identification of mpox lesions using deep learning

INTRODUCTION

Clinical diagnosis of mpox (formerly monkeypox) is sometimes a dilemma due to the rarity of the disease and its similarity with other skin lesions, such as chicken pox, measles, and herpes simplex. This project attempted to address this problem by building a convolutional neuralnetwork (CNN) to distinguish mpox lesions from other skin lesions in a binary classification problem.

DATA COLLECTION AND PROCESSING

Images of mpox, chicken pox, and measles lesions were extracted from two Kaggle datasets (https://www.kaggle.com/datasets/sachinkumar413/monkeypox-images-dataset/data and https://www.kaggle.com/datasets/joydippaul/mpox-skin-lesion-dataset-version-20-msld-v20). The images were cleaned and then augmented. A function was defined to vectorize each image and assign a label to it. Each image vector and its label constituted an array; mpox lesions were labelled 1, while non-mpox lesions were labelled 0. The arrays of all images in each skin lesion folder constituted a list. After treating each folder this way, the three skin lesion lists were combined and shuffled.

MODELING

The data was split into training and testing data, and a CNN was built and fitted to the training data. The CNN used in this project has two convolutional layers, with max pooling applied to each one. The fully connected part of the model has four dense layers, namely the input, two hidden, and the output layer. The input layer has 256 neurons, the first hidden layer has 128, the second hidden layer has 64, and the output layer has 2 as there are two classes of the output variable. ReLu activation was applied to the convolutional layers. In the FC layer, sigmoid activation function was used in the output layer since this was a binary classification problem, while tanh activation was applied to the other layers. The binary crossentropy loss function was applied to the output layer. The model was compiled using RMSprop optimizer with learning rate of 0.01. Batch normalization and dropout regularization were applied to improve the performance of the model.

RESULTS

After 30 epochs, the model achieved 95% accuracy on the training data; however, its performance on the test data was lower (80% accuracy). The loss was 0.13 on the training set and 0.74 on the test set. The area under the receiver operating characteristic curve is 0.87, which is a good score. 

LIMITATIONS

The accuracy of the CNN was not compared with that of physicians or laboratory diagnostic methods. Investigation along this line is warranted in the future to determine whether the CNN developed in this study is superior to or at least as accurate as physicians or laboratory tests.
