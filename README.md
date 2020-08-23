# Sonar object classification

Use 60 features to classify sonar objects through a simple MLP with cross-validation.  
Credit: Deep Learning with Python by Jason Brownlee  
Data source https://raw.githubusercontent.com/jbrownlee/Datasets/master/sonar.csv

The 60 input variables are the strength ofthe returns at different angles.   
The prediction variable is either R for "rocks" or M for "metal cynlinders"  
![dataframe](https://github.com/sindhri/sonar_object_classification/blob/master/doc/img1.png)

## baesline model (2-layers)
The baseline model is a 2-layer MLP with binary cross entropy as the loss function and Adam as the optimizer, using 10-fold cross validtion
The final accuracy rate for the baseline model is: 81.21% (8.67%)

## standardized (2-layers)
Using the same baseline model, but standardized the training variables and fit the validation variables through the same parameters, with the pipeline class  
The final accuracy rate for the standardized model is: 87.05% (6.39%), run again 87.02% (6.82%)

## standardized with reduced neurons (2-layers)
The input has 60 features, but we could try to reduce it to half so force the system to pick the best features.
The accuracy is similar to standardized model: 83.14%, run again, 87.11%(6.64%), similar

## standardized with a deeper net (3-layers)
Add one more layer to see whether it improves the accuracy
The final accuracy of a deepaer net is 88.40% (7.58%), run again, 88.59% (8.20%)  much improved

## reduced neuron with a deeper net (3-layers)
Try to use reduced neuron but a deeper net
The final accuracy for the reduced but deeper net is 88.05% (8.57%), 83.68% (6.47%). not better.

## experimenting with a 4-layer deep net
The final accuracy for the reduced but deeper net is 84.59% (9.89%), 87.54% (6.42%)， not better

## conclusion, the best prediction is standardized with a deeper net