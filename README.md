# Audiobook Customer Prediction

This project involves predicting whether a customer will make another purchase from an Audiobook company based on their historical data. The goal is to predict the likelihood of a customer returning within the next 6 months. By doing so, we can focus advertising efforts on customers most likely to convert, reducing costs and increasing ROI.



## Project Overview

The dataset contains the following features for each customer:
- **Customer ID**: Unique identifier for each customer
- **Book Length Overall**: Sum of all purchase durations in minutes
- **Book Length Avg**: Average length of books purchased
- **Price Paid Overall**: Total amount spent by the customer
- **Price Paid Avg**: Average amount spent per purchase
- **Review**: Whether the customer left a review (Boolean)
- **Review Out of 10**: Rating given by the customer, if applicable
- **Total Minutes Listened**: Total listening time for purchased books
- **Completion**: Fraction of books completed (from 0 to 1)
- **Support Requests**: Number of customer support requests made
- **Last Visited Minus Purchase Date**: Number of days since the last purchase

The target variable is a Boolean indicating whether the customer will make another purchase within the next 6 months.

## Data Preprocessing

Before training the model, the data undergoes several preprocessing steps:
1. **Standardization**: The input features are standardized to have a mean of 0 and a standard deviation of 1 using `sklearn.preprocessing.scale`.
2. **Data Splitting**: The data is split into three subsets:
   - **Training (80%)**
   - **Validation (10%)**
   - **Test (10%)**
3. **Balancing**: The dataset is balanced to ensure that the target classes (0 and 1) are evenly represented.

## Model Architecture

The machine learning model is a feed-forward neural network built using **TensorFlow/Keras**. It has the following architecture:
1. **Input Layer**: 10 features
2. **Hidden Layers**: Two hidden layers, each with 50 units and ReLU activation
3. **Output Layer**: 2 units with a softmax activation to represent the probabilities of the two classes (will buy vs. won't buy)

## Training the Model

The model is trained using the following parameters:
- **Optimizer**: Adam
- **Loss Function**: Sparse Categorical Cross-Entropy
- **Metrics**: Accuracy
- **Batch Size**: 100
- **Epochs**: 100 (Training stops early if there is no improvement)

The model is trained on the training dataset and evaluated on the validation dataset during training.

## Results

Once the model is trained, it is evaluated using the test dataset to determine its performance. The accuracy of the model will be reported based on its ability to predict whether a customer will make another purchase.




