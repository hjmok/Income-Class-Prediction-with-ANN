# Income-Class-Prediction-with-ANN

In this project, an Artificial Neural Network predicts whether an individual has an income above or below $50,000 USD using supervised learning.


## Dataset and Library
PyTorch was used as the main module for this model.
The dataset contains information on 30000 adults, including their education level, occupation, age, marital-status, and several other useful information. The label is whether the individual is earning above or below $50,000 USD. However, the label is uneven with 21700 classified as below and 8300 as above $50,000 USD. 
The dataset be found from in the University of California Irvine Machine Learning repository:

http://archive.ics.uci.edu/ml/datasets/Adult

## Data Preprocessing
Firstly, the data had to be separated from categorical and continuous values. Continuous values included age and hours worked per week, which could directly be converted into tensors to act as inputs into the ANN.

However, categorical columns are all strings which cannot be used as input for the ANN. This includes the sex, education, marital-status, work class, and occupation columns. As such, these columns were all encoded so that they had a numerical value associated with each string, which can then be converted into a tensor to be fed into the ANN.

## ANN Model
The hidden layers went in the order of 192, 96, and 48 neurons. In addition, a dropout rate of 50% was added to each hidden layer. The final output size was 2, using a Sigmoid activation function to predict whether the individual makes above or below $50000.

The loss metric used was Cross Entropy Loss, since this is a mutually exclusive answer problem (label can either be above or below $50000, but not both). The Adam optimizer was used for the model.

## Results
The model was trained for 500 epochs. The model performed well on the test set, being correct 85.75% of the time. However, the loss was still slowly reducing according to the Loss plot. As such, training on a few dozen more epochs could've achieved a marginally better accuracy.

Moreover, the dataset was unbalanced, containing 72% of class 0 (below $50k) and 28% class 1 (above $50k). As such, a training on a more even dataset could provide more insight to the latter label

For the resulting image, please visit: https://hjmok.github.io/josephmok_portfolio/#/Income
