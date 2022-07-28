# MODULE 4 CHALLENGE : Risk Return Analysis

In the challenge we are taking on the role of a quantitative analyst for a FinTech investing platform. This platform aims to offer clients a one-stop online investment solution for their retirement portfolios that’s both inexpensive and high quality. We Have Been Tasked with evaluating four new investment options for inclusion in the client portfolios. 

During this challenge we will be importing data from a csv file by using the read_csv function and path module from pandas. We read the csv file into a dataframe while creating a DateTimeIndex. To prepare our data for analysis we need to drop any missing values with the .dropna() function and to get the daily returns for what we are looking for we use the .pct_change() function. We combine the two in one line because when we do the percent change function the very first line there will be a nan value because there is nothing for it to be compared to so that is why we also use the .dropna() function. 


When analyzing the quantitative performance of the portfolios, we used the .plot() functtion to show the daily returns over the seven years. To calculate the cumulative returns of the portfolios we use the .cumprod() function and the .plot() function to help us visualize those numbers.

When analyzing the volatility we use the .plot() function but this time we include kind="box" to plot a box and wiskers plot. To get a better picture of just the four portfolios we can use the .drop(columns="S&P 500") function to only show the four fund portfolios. Then we used the same method to show the box plot to get a better visualization of the daily returns of just the four fund portfolios. 

When analyzing the risk of the portfolios we look at the standard deviation of the portfolios by using the .std() function. To get the annualized standard deviation we take the standard deviation and multiply it by the square root of the number of trading days. To use the square root in the formuat we use the np.sqrt() function. To plot this we want to use the dataframe on a 21 day window and to do that we use the .rolling(window=21) function before using the .plot() function. 

When analyzing the risk-return profile of the portfolios we need to calculate the annual average return by using taking the average of the daily returns with using the .mean() function and multiplying by the number of trading days. We also need to calculate the sharpe ratios by using the annual average returns that we just calculated and dividing them by the annualized standard deviation, the higher the sharpe ratio the better returns have been relative to the risk it has taken on. We also want to visualize the sharpe ratios via a bar graph so we use the .plot() function and inside that function we specify using kind="bar".

When we are thinking about diversifying our own portfolio we further investigate two funds and I selected Berkshire Hathaway Inc, and Tiger Global management LLC. We want to calculate the covariance of one of these funds we specify their colomn of the daily returns dataframe on a 60 day rolling window and use the .cov() function, and inside that function we specify the column of the S&P 500 since that is what we are trying to compare. To calculate the beta of one of the firms we use the covariance that we just calculated and divide that by the variance of the S&P 500. To plot our results we again use the .plot() function.


---

## Technologies

This project leverages python 3.7 with the following packages:

* [Pandas](https://github.com/google/pandas) - Pandas is a powerfull tool for data analysis and manipulation. Pandas provides a plethora of useful functions that make it easy to express, analyze, and manipulate data.

* [NumPy](https://github.com/google/numpy) - NumPy offers comprehensive mathematical functons, used for working with arrays. NumPy allows for seamless and speedy integration with a wide variety of databases.


---

## Installation Guide

Before running the application first install the following dependencies.

```
import pandas as pd
from pathlib import Path
import numpy as np
```

---

## Usage

To use the risk_return_analysis file simply clone the repository and open the risk_return_analysis.ipynb file in Jupyter Notebook.




Upon opening the file you will have the option to run the whole note book and that will provide you with all of the calculations and visualizations for the perfomance of the four portfolios and the S&P 500.


This is where we created a line plot that displays the daily returns of the four portfolios and the S&P 500. ![Screenshot 2022-07-27 155817](https://user-images.githubusercontent.com/107158380/181413934-4c9fbfdd-4da3-4acd-9f01-c96163439b22.png)

This is where we created a line plot that displays the cumulative returns of the four portfolios and the S&P 500. ![Screenshot 2022-07-27 155848](https://user-images.githubusercontent.com/107158380/181414048-57e2787b-9e16-4a2c-a8ed-5ce4884bb326.png)

This is where we created a box plot that displays the daily returns of the four portfolios and the S&P 500. ![Screenshot 2022-07-27 155914](https://user-images.githubusercontent.com/107158380/181414157-cf418629-a5be-4168-9bcc-d5377e5cf8e4.png)

There are a couple of instances where one or more of the four fund portfolios out performed the S&P 500. However, over the entire span of the seven years, the S&P 500 index has significantly outperformed the other portfolios while finishing on top with a large margin.

This is where we created a box plot that only displays the daily returns of the four portfolios, not the S&P 500. ![Screenshot 2022-07-27 155935](https://user-images.githubusercontent.com/107158380/181414235-902ffa6e-602a-4280-a583-513ad19f409b.png)

Based on the box plot visualization of just the four fund portfolios, the fund that was the most volatile was the Berkshire Hathaway Inc portfolio, and the fund that was the least volatile was the Tiger Global Management LLC portfolio

This is where we created a line plot of the rolling standard deviations of the four portfolios and the S&P 500. ![Screenshot 2022-07-27 155958](https://user-images.githubusercontent.com/107158380/181414339-c8c7cd3f-4bdc-4056-8171-2150ef63a23a.png)

This is where we created a line plot of the rolling standard deviations of only the four portfolios, not the S&P 500.![Screenshot 2022-07-27 160018](https://user-images.githubusercontent.com/107158380/181414441-8c6fd114-fa89-4a1c-a58d-0ed881f82d32.png)

There were a couple of instances of Berkshire Hathaway posing more risk than the S&P 500, but over the entire span of the seven years the S&P 500 portfolio has the highest standard deviation at the start and at the end.

Again, there are some instances where all of the portfolios move with the S&P 500. However, the portfolios generally were not impacted by the movements of the S&P 500. The one portfolio that was most impacted by the S&P 500 would be the Berkshire Hathaway Inc portfolio.
 
Based on the rolling standard deviations of the four fund portfolios, Soros Fund Management LLC started out as the most risky, and Berkshire Hathaway Inc ended as the most risky. Over the majority of the seven years Berkshire Hathaway was the most riskiest portfolio.

This is where we created a bar graph that displays the sharpe ratios of the four portfolios and the S&P 500. ![Screenshot 2022-07-27 160042](https://user-images.githubusercontent.com/107158380/181414545-8f4f32ab-148f-4670-99c9-cc49a82203ca.png)

The portfolio that offers the best risk-return profile would be the Berkshire Hathaway Inc fund, and the portfolio that offers the worst risk-return profile would be the Paulson & CO Inc fund.

This is where we created a line graph that displays the rolling beta of the Berkshire Hathaway Inc. portfolio compared to the S&P 500. ![Screenshot 2022-07-27 160103](https://user-images.githubusercontent.com/107158380/181414721-e45b61dc-70bb-46f6-a927-64125d9eade3.png)

his is where we created a line graph that displays the rolling beta of the Tiger Management LLC portfolio compared to the S&P 500. ![Screenshot 2022-07-27 160127](https://user-images.githubusercontent.com/107158380/181414768-d3d8aba1-4f5e-41c9-89c1-698e14a7ab3b.png)

The Bershire Hathaway Inc portfolio is more sensitive to movements in the S&P 500 due to it having a stronger average beta value.

I would personally recommend for the inclusion of the Bershire Hathaway Inc portfolio due to it have the highest risk-return (sharp ratio), highest anual average returns, and the highest cumulative returns. I would be fine with taking on the risk of this portfolio since it is the only portfolio to even come close to competing with the S&P 500.

---

## Contributors

Completed by Adam Cooke

---

## License

MIT

