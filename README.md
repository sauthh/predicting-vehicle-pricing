# Predicting Vehicle Pricing

This project was a collaborative effort between four people, including me, for a class.

## Introduction

* Not knowledgeable on the topic of Cars
* Second hand cars can vary in price
* Found dataset on Kaggle containing multiple large datasets
* Find out how pricing of cars are affected by its features

## Problem Statement

The process of buying or selling second hand vehicles requires the person to be knowledgeable in the topic. However, due to limited knowledge about second hand market, many individuals often undersell their cars, missing out on potential value. Therefore, it is crucial to inform people about the factors, so they can optimize their gain before they sell or purchase a car.

## Overview

* Contains 8,128 unique rows and 13 columns: name, year, selling_price, km_driven, fuel, seller_type, transmission, owner, mileage, engine, max_power, torque, seats
* Linear Regression - used to establish a relationship between predictor values (such as year, km_driven, mileage, etc) and the target variable (price for the used car)
* Fitting a linear regression model to the data allows us to understand how changes in the predictor variables impact the price of the used cars

## Methodology

* Rows with missing values were deleted
* Removed “kmpl” and ”km/kg” from mileage, “CC” from engine, “bhp” from max_power
* Converted object to integer for fuel, seller_type, transmission, owner, mileage, engine, max_power, seats
* Split data into 70% training, 15% valid, and 15% test
* Dropped name, selling_price, and torque
* Set selling_price as the target value

## Results


## Discussion

* Less kilometers driven sold for higher, fewer owners the better, new cars sell for more
* Dataset contained large amounts of outliers, which throws off the algorithm and may cause some inaccuracy
* Engine, fuel, max_power, etc. may matter less to how much cars sell for as the caused less correlation in price

## Limitation
* Varying degree of experience with coding and algorithm
* Didn’t know how to perform certain actions ie. (remove outliers)
* Narrow focus on Linear regression, overlooking nonlinear relationships, this could negatively impact results as we only used one methodology
* Future work would explore more algorithms
