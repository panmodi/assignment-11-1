# assignment-11-1
Apply the CRISP-DM framework to the provided dataset of 426K used cars. Understand what factors make a car more or less expensive.

Jupyter notebook: [assignment_11_1_PanktiModi.ipynb](https://github.com/panmodi/assignment-11-1/blob/main/assignment_11_1_PanktiModi.ipynb)

Data used: [vehicles.zip](https://github.com/panmodi/assignment-11-1/blob/main/data/vehicles.zip)

#### Business Understanding

Client, used car dealers,  might be manully pricing the inventory. This dataset is considrably large which has information about various traits of a car. We can use data driven approch to determine/predict the car price. We need to answer which features of the car drives the price. e.g. manufacturer, condition, year, state

We can use various models to determine/predict the price of the car. We can use various deatures of the car and take actionable recommendations for the client on which type of cars to acquire and how to proce them effectively. 

#### Data Understanding
* Total rows: 426880
* Total rows where price!=0 : 32895
* As 'fuel', 'transmission' has <1% of data NaN, making NaN data as 'other'
* Column 'condition' has large number of data with NaN. So making them as 'missing'
* Filterted out the data where 'price' is between 0 to 500K. Some rows has really large number which is sked the dataset.
* Code also has commneted line where data is filtered out ninety_ninth_percentile_price(66995.00)
* Made new DataFrame 'data_clean' with few of the columns. e.g. 'id', 'region','price','manufacturer','condition','odometer','state','year'
* Have added few graphs to understand the data

#### Data Preparation

