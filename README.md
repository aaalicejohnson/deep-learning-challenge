# Alphabet Soup - Neural Network Model

## OVERVIEW

The nonprofit Alphabet Soup wants to create a model that will help them determine the best use of their funds. To accomplish this, a CSV containing metadata about different organizations was processed and then fit to a neural network model. This model then can be used to determine and predict whether or not an organization will successfully use the funding. 

## RESULTS

#### Data Preprocessing

The features for the model were the columns that were not the “IS_SUCCESSFUL” columns of the dataframe we created from the CSV and the “IS_SUCCESSFUL” was the target for the model. 

![Alt text](/Images/features.png)

In the original model, we removed “EIN” and “NAME” as they were not considered to be features but rather identifying information. 

![Alt text](/Images/dataframe.png)

#### Compiling, Training, and Evaluating the Model

![Alt text](/Images/model.png)

The model had 80 neurons in the first layer and 30 in the second hidden layer. The model used relu as the activation function  and sigmoid for the output layer. The accuracy was around 73 percent. 

Changes were made to the initial model to improve the accuracy through various attempts. In the first two attempts, we tried adding another hidden layer, changing the activation functions, as well as the number of neurons in the hidden layers. However, this did not yield an accuracy above our target of 75 percent, so we tried changing some of the pre-processing of the data. These changes included: 
* Keeping the “NAME” column and creating bins 
* Removing the “STATUS” an “SPECIAL_CONSIDERATONS” columns based on the count of the unique values being heavily skewed towards 1 of the 2 values: 

![Alt text](/Images/value_counts.png)

I then created a model with 3 hidden layers with 100 nodes in the first layer, 30 in the second, and 20 in the last layer, keeping the activation functions the same. These changes were able to produce a testing accuracy of 78% which was above the target of 75%.

## SUMMARY

Our initial approach did not yield a model with the desired accuracy. By changing our approach to the pre-processing and adding another hidden layer and adding more nodes yielded a model that was above the testing accuracy. Using a RandomForestClassifier model could also solve this classification problem, or Logistic Regression and might produce a similar accuracy without having to account for the different variables of nodes, hidden layers, and activation functions. 


