Stock price prediction

where we use a stm model which is the artificial repairing recurrent neural network the model will be trained on stock price of Google from 2012-2016 and vdp test upon stock price of Google on the month of January 2017

PREPROCESSING

 in part 1 of data preprocessing we import all the libraries and import the training set and take only single feature or column of the training data set as training set.  In iloc we use one column to to get us an 2D array if we use just one when will get a a vector(1D).

for this rnn which will have a sigmoid activation function at the output layer we will use the feature scaling that is normalisation instead  standardization by using the min_Max_scaler class and create the object sc.

Now we will create a structure with 60 timesteps and one output. the previous timetables will be saved in X_train list and the output will be saved in y_train list.

for 1 y_train element(price at a single day) which is present in a single row will have 60 elements in a single row in X_train (price at previous 60 days(timestamps))  on which which will be trained to get the output in the y_train.

like the output(price) 61 is trained On previous 60 timestamps prices  present in X_train.

In X_train  elements are saved as arrays which contains 60 timestamp where as in y_train elements are just numbers not

Finally, those lists are converted into numpy arrays.



Now we will add a new dimension, to add new indicators/features by using reshape function.

RNN takes input as a 3D tensor that is a 3D array with shape [batch, timesteps, feature].Batch size  here training is made with single batch which consists of all the the stock prices from 2012-2016. In time steps which we know it is 60 and in feature we will be only using the 'open' column values in the csv file as feature so we will keep it as 1, if we use any other feature or indicator we can increase it.

Built stacked RNN which consists of dropout regularization various models and layers

BUILDING RNN

we create lstm layer where we use 50 units(neurons). Return_sequence is returned true because it will be use lstm lyer again later. In input_shape, shape has the last two dimensions of the X_train, where each row of X_train is an input for the rnn. Finally, we add a dropout layer to which can drop 20% of the units/neurons for regularising while backpropagating and front propagating.

we are Using 50 units and 4 LSTM layers because to increase the dimensionality of the model.  In the last lstm there we do not use return_sequence=False because it is the default set as false.

Finally we add a output layer which is the dense layer and the units=1. 



x_train-input

y_train-ground truth

epochs-how many times(iterations) we want the model to hold the training data to forward propagate and back propagate to update the weight

first we initialize the real stock price to compare with predicted one later.

we load the the test dataset .To take the the test set inputs we need to use both data from the training and test test because the first date of 2017 will be having dates of the training set (previous 60 days) , now the further dates in the testset  will contain both the prices from training and test set so rather than using the testset  training set we will use the csv data set and concat them to get the values and create a new variable inputs which contains values of the data set which we created previously from last 60 elements of the training set To to the ending

then the input vector is converted into an array and we apply that transform function to it for feature scaling.

Tu predict we need to to use the inputs as a 3D array


now we will create similar X_testdata structure with 60 time steps in each input as we did previously .In range, the second parameter is taken as 80 because there are 20 days(elements) in our test set. 

we will predict the output so there is no y_test and the rest part parts are modified as we did in the previous part and finally  after prediction we apply inverse transform method to the sc class to undo the feature scaling.

Now we plot both, the real and the predicted stock prices.  Here we do not evaluate the model because we wanted to check if our predictions follow the same direction as the real stock price rather than their closeness to real values . Even though we can evaluate our model by using our RMSE( root mean square error) of our prediction problem.
