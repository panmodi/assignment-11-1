# assignment-11-1
Apply the CRISP-DM framework to the provided dataset of 426K used cars. Understand what factors make a car more or less expensive.

Jupyter notebook: [assignment_11_1_PanktiModi.ipynb](https://github.com/panmodi/assignment-11-1/blob/main/assignment_11_1_PanktiModi.ipynb)

Data used: [vehicles.zip](https://github.com/panmodi/assignment-11-1/blob/main/data/vehicles.zip)

#### Business Understanding

Client, used car dealers,  might be manully pricing the inventory. This dataset is considrably large which has information about various traits of a car. We can use data driven approch to determine/predict the car price. We need to answer which features of the car drives the price. e.g. manufacturer, condition, year, state

We can use various models to determine/predict the price of the car. We can use various deatures of the car and take actionable recommendations for the client on which type of cars to acquire and how to proce them effectively. 

### Data Understanding
* Total rows: 426880
* Total rows where price!=0 : 32895
* As 'fuel', 'transmission' has <1% of data NaN, making NaN data as 'other'
* Column 'condition' has large number of data with NaN. So making them as 'missing'
* Filterted out the data where 'price' is between 0 to 500K. Some rows has really large number which is sked the dataset.
* Code also has commneted line where data is filtered out ninety_ninth_percentile_price(66995.00)
* Made new DataFrame 'data_clean' with few of the columns. e.g. 'id', 'region','price','manufacturer','condition','odometer','state','year'
* Have added few graphs to understand the data

### Data Preparation
* Column 'manufacturer' has categorical data so would use OneHotEncoder
* Also split the data in train and test set

### Modeling
* Few models like LinearRegression, Polynomial regression can be used

### Evaluation
* Predict the data with various models used
* pipe_1 is using LinearRegression model on 'manufacturer', 'odometer' with 'price'
* pipe_2 is using LinearRegression model on 'manufacturer', 'odometer','year' with 'price'
* pipe_poly is using Polynomial Regression Pipeline on 'manufacturer', 'odometer' with 'price'
* pipe_poly is also using Polynomial Regression Pipeline on 'manufacturer', 'odometer', 'year' with 'price'
* pipe_2 is also using LinearRegression model on 'manufacturer', 'odometer','condition', 'year' with 'price'

### Deployment


With the model I used pipe_1 which is for Linear Regression model trained on 'manufacturer' and 'odometer' I got following
Train MSE:  216723965.09
Test MSE:  214549394.08
Train RMSE:  14721.55
Test RMSE:  14647.50

My Train and Test RSME are very near. So the performance is similar with Train and Test sets. 
I definately have prediction error higher so the steps I can use to improve are 
The current features 'manufacturer' and 'odometer' are likely insufficient to predict price accurately.
I need to consider 'condition', 'year' etc
I can also look into sked data as dataset has some cars with much higher price



# With pipe_2 model Linear Regression model trained on 'manufacturer', 'odometer' and 'year'
# I got following
# Train MSE:  193902001.04
# Test MSE:  189432576.12
# Train RMSE:  13924.87
# Test RMSE:  13763.45

# Adding year infromation is slightly better than previous model. 

