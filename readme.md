<img style="float: left;" src="./images/fanniemae.png">
<br><br><br><br><br><br>
______

# Mortgage Loan Default Classifier  
____________  
____________  

## Problem Statement    
_____________  
Fannie Mae, or more specifically the Federal National Mortgage Association (FNMA), is a government sponsored entity whose primary goal is to raise home ownership and affordable housing levels.  Fannie Mae attempts to accomplish this in essence by purchasing mortgage loans within certain parameters from mortgage lenders.  In turn, mortgage lenders are provided cash flow to issue additional mortgages.  

The cause of the Financial Crisis of 2008 can in part be drawn back to the purchase of mortgage loans with an actual probability of default that were higher than assumed.  By creating a classification model that will predict whether a mortgage loan will default based on pre-purchase characteristics, Fannie Mae may better avoid high risk mortgage loans.  The model will be evaluated based on Accuracy and False Negative Rate.  In this particular case, the "positive" class will be loans that default therefore, we will seek to minimize the False Negative Rate while maximizing Accuracy.  

## Data  
_________  
Fannie Mae provides 2 options in regards to the data available for download; the entire dataset or subsets per quarter of loan acquisition. The entire dataset encompasses approximately 26 GB of data in comparison to approximately 200 - 500 MB for quarter subsets. The quarter subsets on average contain greater than 200,000 observations which will be sufficient for the scope of this project as the projects current scope seeks predict loan default using the acquisition data.  

The Acquisition file contains static loan characteristics for each loan acquired in the given quarter. In contrast, the Performance file contains the monthly performance such as payment history, loan balance, and final disposition through the entire life cycle of each loan acquired in the associated quarter. Since the intent of the model is to predict loan default before acquisition by Fannie Mae, the model will concentrate on the features from the Acquisition file while only extracting the loan disposition from the Performance file.  

## Model  
_________  
In order to render a better accuracy and false negative rate interaction features and a neural network will be introduced. Correlation between continuous features and whether a loan default were minimal. By using PolynomialFeatures, the model can investgate whether the interaction between these features are of more importance than the feature alone. Additional, a neural network wil be introduced to increase accuracy and decrease the false negative rate. A logistic regressor has an advantage of being able to indentify key features that have the greatest influence in determining whether a loan will default. However, as evidenced by the base model, it may not be able to reach the accuracy needed to be a successful model. A neural network does not have the interpretability inherent in the logistic model however, it has been shown to highly accurate because of their ability to generalise and respond to unexpected patterns. The high degree of inaction between features in this dataset may make a neural network the right choice in this situation.

## Conclusion  
_________  
The neural network model with an adjusted threshold of 0.10 is able to obtain 0.90 accuracy and a false negative rate of 0.074% which far surpasses the benchmark of 0.309%. For reference, Fannie Mae would be able to avoid 235 defaulted loans using this model. Using an average of $50,000 loss per default, this would equate to a loss avoidance of \$11,750,000 per 100,000 loans.