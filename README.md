# Sonar object classification

Use 60 features to classify sonar objects through a simple MLP with cross-validation.  
Credit: Deep Learning with Python by Jason Brownlee  
Data source https://raw.githubusercontent.com/jbrownlee/Datasets/master/sonar.csv

The 60 input variables are the strength ofthe returns at different angles.   
The prediction variable is either R for "rocks" or M for "metal cynlinders"  
![dataframe](https://github.com/sindhri/sonar_object_classification/blob/master/doc/img1.png)

## baesline model
The baseline model is a 2-layer MLP with binary cross entropy as the loss function and Adam as the optimizer, using 10-fold cross validtion
The final accuracy rate for the baseline model is: 81.21% (8.67%)

## standardized
Using the same baseline model, but standardized the training variables and fit the validation variables through the same parameters, with the pipeline class
The final accuracy rate for the standardized model is: 87.05% (6.39%)