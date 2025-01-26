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

After running the algorithm, we were able to run the Mean Absolute Error (MAE), Mean Squared Error (MSE), and 𝑅2 score. Firstly, MAE is the average size of the incorrect predictions in the total predictions, which is 270,259 for valid and 267,826 for test. The selling price ranges from $29,999 to $1,000,000, which means the predictions are off by around 270,000 from the actual selling price on average. Similarly, MSE measures the average of the squares of the errors, thus if the errors are large, the measurement will be exponentially larger. For valid, we got 219,820,858,711 and for test, we received 219,919,915,564. Lastly, the R squared score ranges from 0 to 1 and it measures how well the regression line fits the actual data. We received a score of 68% for the valid data and 66% for the testing data. This tells us that our experiment explains the majority of the variance but there is still room for improvement.

![Results](https://github.com/sauthh/predicting-vehicle-pricing/blob/a3ec09f2a1cdb43c8ba78eaf1a72ba7f13c0b104/Figures/figure5.png)

Next, we graphed the predicted versus selling price with a line of best fit. Majority of the data is congregated around the bottom left portion of the graph and as the price increases, it slowly starts to drift away from the line.

![Actual vs. Predicted Values](https://github.com/sauthh/predicting-vehicle-pricing/blob/20293977fc814973a71a17df42474f98cc467726/Figures/figure6.png)

## Discussion

We believe we have accomplished what we searched out to do from the beginning of the project. Obviously our work was not perfect, but we did the best we could. We found that year, kilometers driven, fuel type, seller type, transmission, owner, mileage, engine, max power, and seats have great influence on the final selling price of the car. While some have minimal influence, they all are a factor in the macro aspect. We are not sure how the dataset was collected, but if the dataset was true for example, it does make sense that these variables matter to people. While not everyone is a car enthusiast or an expert, they still care about the specifications of the car.

One thing we would like to note is that our experiment was heavily limited by our knowledge of python. For example, our dataset contained numerous outliers, which can be seen in the graph to the right as it shows a box plot of the selling price. While having outliers is not necessarily a bad thing, having numerous outliers can negatively impact the algorithm. We were aware of multiple outliers in multiple columns, we did not know how to address them. We do not have much experience with algorithms, thus we were heavily limited on what actions we could take. As a result, for our future work, we would like to gain a better understanding of how to find outliers and how to properly remove them.
