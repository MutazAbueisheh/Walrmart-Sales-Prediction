The objective of this work is to predict the weekly sales for Walmart by using RNN for the dataset : https://www.kaggle.com/datasets/varsharam/walmart-sales-dataset-of-45stores/data

The dataset has information about the Weekly Sales of 45 stores for the year 2010-2012, including the factors affecting Sales such as Holidays, Temperature, Fuel Price, CPI (Consumer Price Index), and Unemployment.

In the notebook, the first step was creating a time series for training and testing, where 20% of the recent data was considered as the test set. The time series is generated with the method generateTrainTestData, which has as arguments the name of the data file, the percentage of test data, the length of the sequences to be generated, and the batch size.

Then, the values of the variables in the time series have been normalized by the generateTrainTestData method. Thus, for a variable x, the variable has been transformed to x’=(x-μx)/σx, where μx is the mean of the variable and σx is the standard deviation.

The only parameter that can be modified for this method is the length of the sequences to be generated. The values of the other parameters must be kept as they are.

The method returns the train and test data, the standard deviation of the weekly sales, and the number of input features.

The output feature (the feature to be predicted) is the weakly sales in 3 weeks.

As an example, if the sequence length is set to 2, each training/test sample will consist of: Weekly_Sales (t-1), Holiday_Flag(t-1), Temperature(t-1), Fuel_Price(t-1), CPI(t-1), Unemployment(t-1), Weekly_Sales (t), Holiday_Flag(t), Temperature(t), Fuel_Price(t), CPI(t), Unemployment(t), Weekly_Sales (t+3). The value to be predicted is Weekly_Sales (t+3).


Strategy for Modeling: Expirementing with several time-series models architectures, then tune the best one

As a result the following table summerizes the expirements and results, knowing that the target MAE (Mean Absolute Error) performace indicator is 68,000:


![image](https://github.com/MutazAbueisheh/Walrmart-Sales-Prediction/assets/161237991/b42874c4-8026-48ea-8ea6-0ddd5f6febb5)
