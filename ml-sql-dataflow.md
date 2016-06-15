# ML-SQL Language Structures


### Assumptions

I will assume we start with a datafile (ex. already have the .csv, .txt, .data, etc.) downloaded locally on our computer. From here our language will be able to perform machine learning tasks on these datasets.


## READ (*file*, *separator*, *header*, *column_names*)

Reads *file* into a matrix to be operated on. The file should be in some CSV like format with values separated by the *separtor*. Additionally the presence of a *header* can be specified along with names for *column_names*.

## REPLACE ([*column_name*, method=*{mean, NaN, nearest_neighbor, etc.}*])

Changes missing or NaN values in specified columns by column mean, 0, NaN, etc. Specified as a list of tuples with the *column_name* and the method*.

## TRANSFORM (*mean_scale*, *variance_scale*, *PCA*=?, etc.)

Used to scale or modify the data that is read in.

## SPLIT (*train*, *test*, *validation*)

Splits the data into training, testing, and validation sets for model building. *train*, *test*, and *validation* can either be percentages that sum to 1 or hard coded values that specify the relative sizes of each of the sets.
    
1. Handle missing values (ex. ?, NA, etc.)
    - remove these examples?
    - set these values to an arbitrary value like 0 or NA
    - replace missing values with the mean

1. Select columns for the regression tasks
    - Select columns I want to use as predictors
    - Select which column am I using as a target (trying to predict)

1. Transform columns or variables
    - create new features from the features we already have (combinations, squaring, cubing, etc.)
    - PCA?
    - scaling?
    
1. Split data into training and testing sets
    - Set a percentage or value for a training or testing set sizes
    - Also create a validation set?
    - Crossvalidation instead?
    
1. Train model using the training data
    - include regularization? (hyperparameter tuning)
    - specify method/ algorithm (lasso, ridge, simple, SVM, etc.)

1. Perform diagnostics on the model
    - See coefficients
    - See metrics like mean squared error, residual sum of errors, r-squared, etc.

1. Test model on held out testing set
    - See metrics like mean squared error, residual sum of errors, etc.
    
1. Visualizations
    - Visualize dataset as a whole (scatter plot matrix)
    - See diagnostic plots (cooks distances, deviances, predicted vs. actual, etc.)
    - bias or variance issues? 
    
1. Repeat for a new model
