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

See the figure below to understand the effect og regularization over 
![Here we can see that that the smaller network starts overfitting later than the reference one (original) and its performace degrades slowly compareed to the original one.](/images/regularization1.png)

Adding weight regularization
The simpler the model, better it is. One way to avoid overfitting is to put contraints on the complexity of a network by forcing its weights to take only smaller values, whcih makes the diftribution of weights more regular. and this is done by adding to the loss function the cost associated with having large weights. the cost come in two flavours:

        1. L1 regularization:here the cost added is proportional to the absolute value of the weights coefficients 
        2. L2 regularization: where the cost added is proportional to the square of the value of the weights 
                                coefficients (weight decay)
![We can see that the model is workign fine here wit l2 regularization. The model is more resistant to overfitting than the reference model (original).](/images/regularization2.png)
![comparing all the regularization methods with the original model without regularization](/images/regularization_methods.png)


Open database (classifying white/red wine based on chemical properties)
---> steps: Data manipulation + data modeling


Processing data:  Split up your data in train and test sets and standardize the data,

Build multi-layer perceptrons for classification tasks,

Compile and fit the data to the models,

Use the model to predict target values, and

Validate the model.

Bonus: Build a model for regression tasks, and fine-tune the model that we built.
 
