---
layout: post
title: Second Post
---

The second project assignment for Data Science Bootcamp involved developing a linear regression model using data that we scraped from a website of our choosing.   

**Overview**

J.D. Power awards have been featured in car advertising for as long as I can remember, and they have recently become more prevalent, thanks to a series of TV ads produced by Chevrolet. The ads purport to show “real people” reacting to the number of J.D. Power awards a given Chevy model has received.  

Obviously, Chevy believes that consumer car buying behavior is influenced J.D. Power ratings and awards.  

The goal of my project was to understand the relationship between J.D. Power ratings and future US auto sales.  

The model I developed was based on 2016 vehicle characteristics including Brand, Type, Price and Fuel Efficiency as well as the JD Power Overall Quality, Overall Performance and Design, and Predicted Reliability Ratings sourced from the J.D. Power website (www.jdpower.com). The model predicted 2017 US auto sales sourced from the Cars Sales Base website (www.carsalesbase.com).  

Limitations included the lack of marketing spend data and the limited size of the modeling dataset (175 observations after exclusions for missing data that couldn’t be inferred).  


**Analysis**

As expected the R-Squared value wasn’t great for the initial model. During the exploratory data analysis, I noticed that the sales volume for pickup trucks was significantly higher than for any other type of vehicle.  


|            Description            | Number of Features | Adjusted R-Squared |
| --------------------------------- |:------------------:| ------------------:|
| Initial Linear Regression         |          7         |        0.248       |
| Linear Regression (Winsorization) |         11         |        0.384       |


Using Winsorization to censor the higher sales volume associated with pickup trucks resulted in a better model.  

I did evaluate simply excluding Pickup Trucks from the dataset but that resulted in a lower Adjusted R-Squared than the Winsorization approach.  

I did not try any Regularization methods since it would make it more difficult to interpret the model coefficients(i.e. to understand the impact JD Power ratings on sales).  

![alt text](https://github.com/jphoskins55/jphoskins55.github.io/tree/master/_posts/Windsorized.png "Logo T

Looking at the plot of predicted vs. actual sales we can see the impact of censoring the data with Winsorization.

![alt text](https://github.com/jphoskins55/jphoskins55.github.io/tree/master/_posts/Chart2.png "Logo T

If we look at the relative contribution of the features in the model we see that the JD Power Overall Quality Rating isn’t the most important variable in the model, but it does have a positive effect (which is what we would expect).  

The relative contribution was determined using the Variable Inflation Factor (VIF) calculation for the model coefficients.  


**Model Interpretation**

The key insight from the model is that each point increase in a vehicle’s Overall Quality rating equates to an estimated 1,677 additional sales.  

The reason this is important is that you can estimate the ROI associated with investments in efforts designed to improve vehicle quality.  

