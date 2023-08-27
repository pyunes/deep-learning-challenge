# Module 21 Challenge

## Overview of the Analysis

* Purpose of the analysis:
* The foundation has a dataset of over 34,000 previous projects funded, each with multiple features. These features, ranging from organization type, industry, sector, amount requested, use case... among other variables; using tensorflow a model will be created to predict which project is more likely to receive funds. If the foundation is able to reliably assess which features are associated with projects that are likely to fail, then it will avoid funding risky projects which will contribute effectively use the funds provided. Traditional statistical methods or basic machine learning models struggle to capture the relationship between the features and the outcome of the project. Deep learning is more likely to be able to model complex non-linear relationships. Specifically, a neural network can potentially capture interactions between features that simpler models might overlook.
  
* Target variable: IS_SUCCESSFUL
                    This variable has 2 possibilities, either successfull or not successfull. It is what the model wants to predict based on the features.
  
* Features: Application type, Affiliation, Classification, Use_Case, Organization, Status, Income_AMT, Special_Considerations, Amount requested 
 
  The model should identify when a project is unlikely to be unsuccesful. If e.g. it requires a lot of resources, it is a Trust, Use case is Healthcare, it has no Affiliation... issues like that could be identified by the model as factors that are associated with success or failure of the project.

##Steps

First, the dataset was loaded and explored to understand its structure and the types of data it contains.

Columns that were not beneficial, like 'EIN' and 'NAME', were dropped.

  *Those columns are considered identifiers that are not useful to predict the target variable
  
Categorical variables like 'APPLICATION_TYPE' and 'CLASSIFICATION' were binned 

  *This avoids having a very large amount of columns and keeps only the most relevant APPLICATION_TYPE and CLASSIFICATIONs to the model.
  
Categorical variables in the dataset were converted into binary features using pd.get_dummies()

  *This is the format that could be used as input for the neural network. 
  
The dataset was split into features (X) and target (y) arrays.

  *E.g.'IS_SUCCESSFUL' was identified as the target variable, and the remaining columns were considered as features for the model. }
  
Training and testing sets were created using the train_test_split function from scikit-learn.

  *This ensures that the model can be validated on unseen data after training.
  
Features were scaled using the StandardScaler to normalize the data.

  *This ensures that no variable has more influence than another.
  
Define model architecture: 

  *The architecture included an input layer, two hidden layers with ReLU activation functions, and an output layer with a sigmoid activation function for binary classification.
  
Validation:

  *After training, the model was evaluated using metrics like loss and accuracy on the test set. These metrics provide a quantitative measure of how well the model is likely to perform on unseen data.

*Interpretation

The model was able to predict the outcome in unseen data with an accuracy of 72%.

![image](https://github.com/AlanIslasMorris/deep-learning-challenge/assets/70079035/3e67cfc1-e455-4283-9556-26cff1f3473d)

#Optimization

 Increasing neurons,
 
    *I tried to use as much as 100 neurons for the first 3; then 50 for the next one; then 30 for the 5th onte and 1 for the output layer.
    * First I just increased the neurons from 50 to 80; then up to 100 and I started adding layers.
    
 Increasing layers, 
 
    * I tried to add layers one by one until I got to 5 layers.
    
 Changing activation function,
 
    * I tried relu for the first three layers, then tanh then sigmoid
    * I tried relu for the first two layers, then tanh then sigmoid
    * I tried relu for the first two layers, then sigmoid then sigmoid
    * I tried relu for the first 3 layers, then sigmoid for the output layer

Reducing the amount of unique values in CLASSIFICATION and APPLICATION_TYPE columns

    * For the classification column I changed the number of unique values by changing the list to replace e.g. filtered_counts_less_than_2 = classification_counts[classification_counts <= 2] instead of less than 1; then I tried less than 5 and less than 6.
    
    * For the APPLICATION TYPE column I tried:
          application_types_to_replace = ['T9', 'T13', 'T12', 'T2', 'T14', 'T25', 'T15', 'T29', 'T17']
          application_types_to_replace = ['T14', 'T25', 'T15', 'T29', 'T17']
          and 2 more different lists.
          
  This had an impact in the number of columns that were used as input for the model. Changing this allows the model to focus on the most common application types and classifications.

Conclusion

The model allowed predicting the outcome with a maximum accuracy of 74% despite different architectures and preprocessing strategies were tried.
          

 
  
