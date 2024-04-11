# Analysis Report
## Overview
The purpose of this analysis was to develop a model that would help Alphabet Soup select the applicants for funding who had the best chance of success in their ventures. The dataset  contained more than 34 thousand organizations that received funding in the past. The dataset had the following information:
* Application type
* Affiliated industry sector
* Government organization classification
* Organization type
* Income amount
* How much funding they were asking for
* whether the organization used the money effectively

## Results:
 * Data Preprocessing
   * What variable(s) are the target(s) for your model?
     * The target variable is "IS_SUCCESSFUL" from the application dataframe
   * What variable(s) are the features for your model?
     * The feature variables are every other column from application_df --> this was defined by dropping the 'IS_SUCCESSFUL' column from the original dataframe
   * What variable(s) should be removed from the input data because they are neither targets nor features?
     * When I tried dropping both EIN and NAME the model's results were short of the 75% target accuracy. After adding NAME back in and binning, the model's accuracy increased to 76%.

 * Compiling, Training, and Evaluating the Model 
   * How many neurons, layers, and activation functions did you select for your neural network model, and why?
     * Model 1 had 5 layers with each layer having a different number of nodes. Only the first three layers had a relu activation shape while the last layer had a sigmoid shape. This resulted in an accuracy of 72%.
     ![Model 1.png](Model%201.png)
     * Model 2 had 4 layers with each layer having a different number of nodes. Only the first three layers had a relu activation shape while the last layer had a sigmoid shape. This resulted in an accuracy of 64%.
     ![Model 2.png](Model%202.png)
     * Model 3 also had 4 layers with each layer having a different number of nodes. Only the first three layers had a relu activation shape while the last layer had a sigmoid shape. This resulted in an accuracy of 76%.
     ![Model 3.png](Model%203.png)
   * Were you able to achieve the target model performance? 
     * Yes
   * What steps did you take in your attempts to increase model performance?
     * Added back the NAME column and binned
     * Adjusted the cutoff values
     * Reduced the number epochs from 100 to 50
     * Decreased the number of layers

## Summary:
Using deep learning 3 models were created, with the final model having an accuracy score of 76%. Further analysis should be completed to see if other shapes, features, or the number of hidden layers or neurons  would be able to improve the prediction of the dataset better. Given the accuracy of the above models, I recommend the third one and further testing may give even more accurate predictions.