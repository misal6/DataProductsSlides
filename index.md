---
title       : Stock Market Futures
subtitle    : Forecasting major European Indexes
author      : Misal6
job         : Stock Futures Analyst
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : solarized_light
mode        : standalone
--- .quote
## Motivation
<q> Weather you are a Fund manager having billions in your portfolio,<br> or an employee contributing to 401K plans which invests in stocks,<br> knowing the direction and <b><font color="darkblue">future returns</font></b> on your invested capital is of vital interest.</q>

--- .quote
## Projection
<p>Suppose you want to invest <b><font color="darkblue">100</font></b> pounds in London Stock market (FTSE). <br>
You would want to know whats the typical return after one year on your investment.<p>


```
## [1] "Return on Investment : 8%"
```

Expect your investment to be <b><font color="darkblue">108</font></b> pounds at the end of one year.

Code:
```
library(datasets)
library(forecast)
idxdata=ts(EuStockMarkets[,"FTSE"])
idxarima=auto.arima(idxdata)    
fcst=forecast(idxarima,h=260)
resfcst=tail(as.data.frame(fcst),1)
curval=round(tail(idxdata,1))
fctval=round(resfcst[,1])
pct=round(((fctval-curval)/curval)*100)
```

---
## Solution
If you wanted to compare major indexes and project for variable time lengths, the solution is an interactive dashboard that will allow you to "choose" and "produce" as per you requirement.

This is specifically the purpose of this simple web base application which can be accessed from anywhere and from any device connected to the internet.

<a href="https://misal6.shinyapps.io/stock_index_forecast/">Stock Market Futures</a>

---
## Wrapup

Thank you for visiting this app.

Complete code for the application is <a href="https://github.com/misal6/DataProductsCoursera">here.</a>

Code that produced these slides is <a href="https://github.com/misal6/DataProductsCoursera">here.</a>

This is the Data Products course project for Coursera.
If you would like to develop great data products, <a href="https://www.coursera.org/specialization/jhudatascience/1?utm_medium=listingPage">this</a> is the best place to start.
