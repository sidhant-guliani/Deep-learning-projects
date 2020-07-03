## Deep learning projects
The projects includes the online available (mainly kaggle/keras) datasets. Following is the information about the jupyter notebooks.

### 1_classifying_movie_reviews.ipynb
I this section we are using IMDb dataset, the IMDB sentiment classification dataset consists of 50,000 movie reviews from IMDB users that are labeled as either positive (1) or negative (0).
Data preparation
right now the data is in form of list, we need to turn it to tensor. we can use one hot encoder, that will convvert them into vectors of 0's and 1's. example: this would mean for instance turning the sequence [3, 5] into a 10,000-dimensional vector that would be all-zeros except for indices 3 and 5, which would be ones. Then we could use as first layer in our network a Dense layer, capable of handling floating point vector data.
Summary: To prevent overfititng in neural networks following are the standard techniques:
Number | Technique
------------ | -------------
1 | Getting more training data.
2 | Reducing the capacity of the network.
3 | Adding weight regularization.
4 | Adding dropout.

![Here we can see that that the smaller network starts overfitting later than the reference one (original) and its performace degrades slowly compareed to the original one.](/images/regularization1.png)

Here we can see that that the smaller network starts overfitting later than the reference one (original) and its performace degrades slowly compareed to the original one.

Adding weight regularization
The simpler the model, better it is. One way to avoid overfitting is to put contraints on the complexity of a network by forcing its weights to take only smaller values, whcih makes the diftribution of weights more regular. and this is done by adding to the loss function the cost associated with having large weights. the cost come in two flavours:

        1. L1 regularization:here the cost added is proportional to the absolute value of the weights coefficients 
        2. L2 regularization: where the cost added is proportional to the square of the value of the weights 
                                coefficients (weight decay)
![We can see that the model is workign fine here wit l2 regularization. The model is more resistant to overfitting than the reference model (original).](/images/regularization2.png)

We can see that the model is workign fine here wit l2 regularization. The model is more resistant to overfitting than the reference model (original).

![comparing all the regularization methods with the original model without regularization](/images/regularization_methods.png)

In the figure above, comparing all the regularization methods with the original model without regularization.

### 2-Predicting_house_prices.ipynb
here we are going to discuss about the 'regression', which consists of predicting continuous values instead of discrete labels.We are going to use the Boston housing Price dataset. The feaures present in the dataset:-

1. Per capita crime rate. 
2. Proportion of residential land zoned for lots over 25,000 square feet. 
3. Proportion of non-retail business acres per town. 
4. Charles River dummy variable (= 1 if tract bounds river; 0 otherwise). 
5. Nitric oxides concentration (parts per 10 million). 
6. Average number of rooms per dwelling. Proportion of owner-occupied units built prior to 1940. 
7. Weighted distances to five Boston employment centres. 
8. Index of accessibility to radial highways. 
9. Full-value property-tax rate per $10,000. 
10. Pupil-teacher ratio by town. 1000 * (Bk - 0.63) ** 2 where Bk is the proportion of Black people by town. lower status of the population.

Here we are going to work on a different approach called K-fold validation. In this the avaliable data is split into K partitions(k=4 or k=5), then instantiating k identical models and training each one on k-1 partiitions while evaluating in reamaining partition.

![](/images/k-fold_cross_validation.png)
![](/images/k-fold_cross_validation2.png)

Summary:
#### Using K-fold approach
One way we saw in earlier notebook to find overfitting and underfitting was looking at the validation/training loss and accuracy and then adjusting the epochs based on that. We could split the data in training and validation set but whn we have fewer data points then the validation set is very small. the onsequence is that the validation scores may change a lot depending on what data points did we chose to use for validation. THE VALIDATION SCORE MIGHT HAVE LARGE VARIATION with regard to validaition split. so we cant rely on that.



### Keras example notebook
question: can you predict whether a wine is red or white by looking at its chemical properties? Open database (classifying white/red wine based on chemical properties)
The accuracy acieved by the model is:accuracy: 0.9984. 
Following are the features in dataset:
fixed acidity', 'volatile acidity', 'citric acid', 'residual sugar','chlorides', 'free sulfur dioxide', 'total sulfur dioxide', 'density', 'pH', 'sulphates', 'alcohol', 'quality', 'type'

Steps to classify the winne base don the features provided:-
1. Processing data:  Split up your data in train and test sets and standardize the data,
2. Build multi-layer perceptrons for classification tasks,
3. Compile and fit the data to the models,
4. Use the model to predict target values, and
5. Validate the model.
6. Bonus: Build a model for regression tasks, and fine-tune the model that we built.

![](/images/wine_model_correlation_matrix.png)


