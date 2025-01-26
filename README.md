# Predicting Vehicle Pricing

This project was a collaborative effort between four people, including me, for a class.

## Problem Statement

The process of buying or selling second hand vehicles requires the person to be knowledgeable in the topic. However, due to limited knowledge about the second hand market, many individuals often undersell their cars, missing out on potential value. Therefore, it is crucial to inform people about the factors, so they can discern the optimal selling price before they sell or purchase a car.

## Dataset

Our dataset was sourced from Kaggle like many others and it was one of multiple datasets within the downloaded zip folder; however, we chose the file with the most data points. It contains 8,128 unique rows and 13 columns: name, year, selling_price, km_driven, fuel, seller_type, transmission, owner, mileage, engine, max_power, torque, and seats. Additionally, there are 9 objects, 3 integers, and 1 float column. As the image below shows, some rows have null values, also known as missing values.

![Data Columns](https://github.com/sauthh/predicting-vehicle-pricing/blob/20293977fc814973a71a17df42474f98cc467726/Figures/figure1.png)

## Methodology

The source we downloaded from contained multiple datasets; however, we decided to use the one with the most amount of data fields. The dataset had numerous missing values and improper fields, which left us with filling in the missing values or deleting them. We chose to delete the rows with missing values, as it was easier for us. Then, we started converting data objects into integers. For example, for seller type, Individual was converted to 1, Dealer to 2, and Trustmark Dealer to 3. For fuel, Diesel was turned to 1, Petrol to 2, LPG (Liquefied Petroleum Gas), and CNG (Compressed Natural Gas) as 4. For transmission, Manual was turned to 1 and Automatic was turned to 2. Lastly, for owner, First Owner was changed to 1, Second Owner to 2, Third Owner to 3, Fourth & Above Owner to 4, and Test Drive Car to 5. Next, columns such as mileage, engine, and max_power contained improper data, so the unnecessary text after the integers were removed such as kmpl, km/kg, CC, and bhp. Afterward, all the previously mentioned columns were converted to integers or floats. Next, we took 70% of the data as training, 15% as testing, and 15% for validation. We chose to run a linear regression algorithm because it establishes a relationship between predictor values (such as year, km_driven, mileage, etc.) and the target variable. Before we ran the linear regression algorithm, we removed name and torque from fields as we believed them to be unnecessary to our testing and set the target variable as selling price. Then we ran the linear regression algorithm, graphed the actual vs predicted values and ran some test metrics.

## Results

Before we went deeper into our investigation, we conducted some basic operations on our data because we wanted to understand our dataset first.

Firstly, the selling price versus kilometers driven graph shows a right skew. It shows an exponential decline graph that proves the more kilometers a car has, the lower the selling price.

![Selling Price vs. Kilometers Driven](https://github.com/sauthh/predicting-vehicle-pricing/blob/20293977fc814973a71a17df42474f98cc467726/Figures/figure2.png)

The owner versus kilometers driven shows that if a car has been passed through multiple owners, it also tends to sell for less. In the graph, 1.0 refers to the first owner, 2.0 as second owner, 3.0 as third owner, 4.0 as fourth and above owner, and 5.0 as test drive car.

![Owner vs. Kilometers Driven](https://github.com/sauthh/predicting-vehicle-pricing/blob/20293977fc814973a71a17df42474f98cc467726/Figures/figure3.png)

Lastly, the year versus selling price graph shows that newer cars sell for a higher price. Cars made in 2020 sell for vastly more compared to ones built in the late 90’s or 2000’s.

![Year vs. Kilometers Driven](https://github.com/sauthh/predicting-vehicle-pricing/blob/20293977fc814973a71a17df42474f98cc467726/Figures/figure4.png)

Accuracy: Correctly classified out of total instances <br/>
Precision: True positive predictions out of all positive predictions <br/>
Sensitivity: Proportion of true positives predictions out of all positives <br/>
F1 Score: Average of precision and recall

![Results](https://github.com/sauthh/predicting-vehicle-pricing/blob/20293977fc814973a71a17df42474f98cc467726/Figures/figure5.png)

![Actual vs. Predicted Values](https://github.com/sauthh/predicting-vehicle-pricing/blob/20293977fc814973a71a17df42474f98cc467726/Figures/figure6.png)

## Discussion

* Less kilometers driven sold for higher, fewer owners the better, new cars sell for more
* Dataset contained large amounts of outliers, which throws off the algorithm and may cause some inaccuracy
* Engine, fuel, max_power, etc. may matter less to how much cars sell for as the caused less correlation in price

## Limitation
* Varying degree of experience with coding and algorithm
* Didn’t know how to perform certain actions ie. (remove outliers)
* Narrow focus on Linear regression, overlooking nonlinear relationships, this could negatively impact results as we only used one methodology
* Future work would explore more algorithms
