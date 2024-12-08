# **Sales Forecasting Project**

## **Objective**

The goal of this project is to predict future sales trends and optimize inventory management using historical sales data with the ARIMA (AutoRegressive Integrated Moving Average) model.

## **Data**
The project utilizes historical sales data, which is expected to be in CSV format. The data should include the following columns:

+ `date:` The date of the sales record.
+ `store:` The identifier for the store.
+ `item:` The identifier for the item.
+ `sales:` The number of sales made on that date.

## **Model**
<p>This project implements the ARIMA model for time series forecasting.</p> 
<p>The ARIMA model was fitted to the historical sales data, which is a standard approach for time series forecasting.</p>
<p>The steps involved in the process include:</p>

### **1. Data Preprocessing:**

+ Load CSV data into a Pandas DataFrame.
+ Group data by store and item.
  <p>Segmentation is essential because different stores may exhibit unique sales patterns influenced by factors such as location, customer demographics, and inventory levels. By isolating each store-item group, the ARIMA model can be tailored to capture these distinct trends, improving the accuracy of forecasts.</p>
+ Ensure the data is sorted by date and set the date as the index.
  <p>Ensuring the data is chronologically ordered so that the model can effectively analyze past sales patterns and make accurate forecasts.</p>
### 2. Stationarity Check:
+ <p>Conduct an Augmented Dickey-Fuller (ADF) test to check for stationarity. This check is necessary to assess if the series is non-stationary, it may indicate trends or seasonality, necessitating further preprocessing for accurate forecasting.</p>

The stationarity check revealed that the sales data for certain store-item combinations exhibited non-stationarity, indicated by a p-value greater than 0.05. This suggested the presence of trends or seasonal patterns in the data. To address this, differencing was applied to the sales data, transforming it into a stationary series.
### 3. Differencing:

+ If the data is not stationary, apply differencing to stabilize the mean of the time series.
  <p>By subtracting the previous observation from the current observation, we create a differenced series. This process helps stabilize the mean and variance, making it easier to model with ARIMA, which assumes stationarity</p>
### 4. Cross-Validation:

+ Use TimeSeriesSplit from Scikit-learn to perform cross-validation on the time series data.
  <p>TimeSeriesSplit from Scikit-learn is employed to evaluate the performance of the model.</p>
### 5. Model Fitting:

+ Fit the ARIMA model to the training set.
### 6. Forecasting:

+ Generate forecasts for the specified number of future time steps.
___
## Usage
1. Clone the repository. `git clone https://github.com/yourusername/sales-forecasting.git
cd sales-forecasting`

2. Prepare your CSV data file and place it in the project directory.

3. Run the Jupyter Notebook:

`jupyter notebook Sales_Forecasting.ipynb`
<p>Follow the instructions in the notebook to execute the forecasting steps.</p>

___
## Results
<p>The results of the forecasting will be visualized using Matplotlib.</p> <p>The plots will display both historical sales data and forecasted sales for each store-item combination.</p> 

### Stakeholder Insights:

The analysis of forecasted trends provides stakeholders with valuable insights for decision-making regarding inventory management, promotional strategies, and resource allocation.
### Model Evaluation:

The model's accuracy is assessed using metrics like Mean Absolute Error (MAE) and Mean Squared Error (MSE), ensuring the reliability of predictions.
### Operational Efficiency:

The insights gained from the forecasting can enhance operational efficiency and potentially drive business growth.

***
## Technology Stack
+ Python
+ Pandas
+ Scikit-learn
+ Matplotlib
***


