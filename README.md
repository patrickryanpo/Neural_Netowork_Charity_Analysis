# Neural_Netowork_Charity_Analysis
Deep Learning

## Overview

A charitable organization called Alphabet Soup is seeking to create an analysis that would predict success in organizations that will effectively allow them to decide which projects to finance. The goal is to create a model using deep neural networks that is 75% accurate. The dataset used was provided by Alphabet Soup and contained over 30,000+ rows collected from previous projects that the charitable organization has financed. 

## Results

### Data Preprocessing
- The dataset provided included information on, success of the project, application type, affiliation, classification, use case, organization type, status of project, income amount, special considerations, and amount ask. 

![AlphabetSoup Dataframe]()

- Due to the nature of the analysis, both EIN and NAME columns were dropped as they do not impact our analysis. 
- The target model was the column: "IS_SUCCESSFUL"
- Features of the model were: "APPLICATION_TYPE", "AFFILIATION", "CLASSIFICATION", "USE_CASE", "ORGANIZATION", "STATUS", "INCOME_AMT","SPECIAL_CONSIDERATIONS", "ASK_AMT"

Preparing the Data for Training: 

- Our first step to training the model was to create bins for both classification and application type columns. We grouped data in these categories that did not appear as many times as the others. 

- Then we used the encoding method to conert categorical columns into numerical values, which allows our model to recognize the data. 

![MergedandEncoded]()

- Then we split the data set by creating training and testing values. After which, we scaled out data using the StandardScaler().

### Compiling, Training, and Evaluating

**Attempt 1**
![DensityChart1]()

In our first attempt, we had three hidden layers with activation relu, relu, and sigmoid. Our hidden layers had neurons of 200, 50, and 20, respectively. 200 Epochs was run in this optimization attempt. 

![Optimization Attempt1]()

As seen above, our first attempt reached an accuracy of 72.23%. 

**Attempt 2**

![DensityChart2]()

In our second attempt, we kept the number of hidden layers as it was in attempt 1 but changed our activation sequence to all relus. Also, we changed the number of neurons to 200, 75, and 30. Ran the model with w00 epochs. 

![OptimizationChart2]()

Our model produced lower result accuracy of 71.79%.

**Attempt 3**

![DensityChart3]()

In our third attempt, we added another hidden layer, which increased our number of layers to 4. Our activation sequence was relu, tanh, sigmoid, sigmoid with values of 250, 150, 30, 20, respectively. The number of epochs run was kept similar to attempt 2 at 150. 

![OptimizationChart3]()

This model produced better results than attempt number 2, however, was lower than our first attempt. The accuracy of this model was at 72.02%. 

**Attempt 4**

![DensityChart4]()

In our final attempt, we used the combination of relu, relu, tanh, sigmoid with values of 200, 150, 30, 20, respectively. This attempt was run at 200 epochs.

![OptimizationChart4]()

This model produced an accuracy score of 72.14%, which was higher than the previous two attempts but did not reach 75%. 

***After 4 attempts, we did not reach our goal of 75% accuracy for this model***

## Summary 

In the end, we did not reach our goal of 75% accuracy for the model. One way to improve the model would be to get the weight of each feature and drop the insignificant ones. However, this method would entail speaking with the execs at Alphabet Soup to find out the significance of these features to their organizational decision making. Another option to improve the model's accuracy would be to use the Support Vector Machine (SVM) as this model is highly preferred and known to produce more accurate results. 


