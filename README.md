# bank_identity_applications
Identifying with supervised model fraudulent bank applications. Had to deal with having very few of the target variable so we did ways of oversampling in this project as well.

In this project, we were provided with a dataset consisting of 1 million rows and 10 fields, including a fraud label which could be used to train a supervised machine learning algorithm to recognize records that should be classified as fraudulent applications to a bank. We began by performing a preliminary analysis of the data, and then built a supervised model to predict whether or not a record should be classified as fraud.

First, we performed a descriptive analysis by building a data quality report to ensure the data was properly organized and ready for further analysis. For each variable we were provided, we examined its distribution and summary statistics. Here's an example of a distribution we found for social-security number.

<img width="948" alt="Screen Shot 2021-07-28 at 12 10 43 PM" src="https://user-images.githubusercontent.com/68137802/127381917-ff790649-1c9a-454a-ab10-0fa35827fecb.png">

After gaining an understanding of the data and ensuring its integrity, we began constructing additional features that would serve as candidate variables for our predictive model. These engineered features were designed to illuminate typical signals of fraud in real life scenarios. An example would be ‘address_count_0_by_30’ which would tell us how many times an address has been seen in the same day versus how many times that same address has been seen in the past 30 days.

Once we’d engineered 365 additional candidate variables, we began the process of reducing dimensionality and identifying the few variables that best distinguished between fraudulent and non-fraudulent records. By first using a filter that combined the rank for the univariate KS and fraud detection rate scores for each variable, we were able to determine a subset of 80 variables that were good model input candidates. We further narrowed this list down to 30 using a logistic regression backwards selection wrapper. Here's a list of some of the final variables we used.

<img width="594" alt="Screen Shot 2021-07-28 at 12 12 08 PM" src="https://user-images.githubusercontent.com/68137802/127382106-81667b62-86ea-4e03-bcb9-1bbabfbbae4b.png">


Using our final 30 variables, we trained random forest, neural network, logistic regression and boosted tree models and adjusted various hyperparameter settings to fine tune each model. After model training, we evaluated the models’ performance on the training, test, and out of time data and selected the model with the best performance on the out of time data, which most closely resembles how well the model will perform when applied in practice to incoming applications. Here are a results of the models we used.

<img width="612" alt="Screen Shot 2021-07-28 at 12 12 38 PM" src="https://user-images.githubusercontent.com/68137802/127382169-b56ef4b5-163d-43a4-89e5-cdcc839a9c3f.png">

We are confident that our data cleaning, feature engineering, feature reduction, and model building processes could be applied to almost any credit card application database and result in a model that can helpfully classify potentially fraudulent applications before they get approved.
