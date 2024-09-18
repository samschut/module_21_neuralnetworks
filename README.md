# module_21_neuralnetworks

In this module we looked at a charity dataset and if the charity was successful based on application type, affiliation, classification, use case, organizaiton, status, income amount, special considerations, and ask amount. In order to use the specific dataset all of the column types need to somehow be turned into a binary dataset. In order to do this a getdummies function was used in order to create a binary dataset to better use the neural network machine learning models available. 

Some other preprocessing of the data was necessary.
-Target Variable: the "IS_SUCCESSFUL" is what is trying to be predicted based on other variables within the dataset given the known successes and unsuccesses of the dataset. 
-Feature Variables: All the other columns are used to determine if a charity is going to be successful, 'APPLICATION_TYPE', 'AFFILIATION', 'CLASSIFICATION', 'USE_CASE', 'ORGANIZATION', 'STATUS', 'INCOME_AMT', 'SPECIAL_CONSIDERATIONS', 'ASK_AMT'
-Variables Removed: The EIN and Name were removed because these can make things slower and should not have an impact on whether the charity is successful or not, they are unique values that would not have any benefit including them.

Campiling, Training, and Evaluatin the model
I ran a total of 5 models, each one seemingly worse than the others. I wanted to try different types of models (ei. relu. sigmoid) to see if any would be a better fit for this data. 
-Model 1: first hidden: relu: 64, second hidden: relu: 32, outer: sigmoid: 1, I just ran 10 epochs with 32 batches to see how this model worked. I got a 63% accuracy which I thought was good for a start.
-Model 2: first hidden: sigmoid: 100, second hidden: sigmoid: 50, outer: sigmoid: 1, I ran 100 epochs to assist with a more accurate train and batch size of 32 again. I went down about 10% so I did not like this model.
-Model 3: first hidden: tanh: 200, second hidden: tanh: 100, outer: sigmoid: 1, I ran epoch 50 and batch size of 32 to help decrease the time and I wanted to see if it was a better model than the previous 2. It has an accuracy of 58% which is better than model 2 but not as good as model 1. 
-Model 4: I figured relu was the way to go at this point and decided to increase the nodes first hidden: relu: 500, second hidden: relu: 250, outer: sigmoid: 1 and ran an epoch of 500 with a batch size of 20. I figured this would be so sensitive and well trained since it took over an hour to run this model. It was uch worse than all the models previous to it. This must have added too much complexity in with all the extra nodes. It was only at 41% accuracy. 
-Model 5: I was a bit more conservative at this point with my nodes. first hidden: relu: 50, second hidden: relu: 25, outer: sigmoid: 1, and an epoch of 100 with a batch size of 20. This was the best model overall with a 67% accuracy. 

I am not sure why I could not get to the target accuracy. After having spent many hours waiting for the training I tapped out. I am not sure if the scaling was not enough or if there was not enough of a correlation with the given data. I wander if the names were kept if there would have been a better correlation. This may be due to an organization being more familiar with the population therefore being more successful based on this regardless of the other variables within the dataset. I would really like to explore this dataset more without taking out any information, at least the name, to determine if there is an impact on the data. 
