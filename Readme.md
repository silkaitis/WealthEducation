# Wealth and Education Investigation

**Purpose**

The purpose of this investigation is to assess gross domestic product as a predictor of school life expectancy using a linear regression. School Life Expectancy is a measure of how many years of education a child of school entering age would receive during the life time if the school enrollment rates stay the same as of today [[1]](https://en.wikipedia.org/wiki/School_life_expectancy). Gross domestic product (GDP) is a monetary measure of the market value of all final goods and services produced in a period (quarterly or yearly) [[2]](https://en.wikipedia.org/wiki/Gross_domestic_product).

**Learning Objectives**

* Scrape data from a website using Requests and BeautifulSoup
* Import / export data from different sources using Pandas
* Build a linear regression model using Statsmodels

**Method**

School life expectancy was scraped from an archived [UN website]('http://web.archive.org/web/20110514112442/http://unstats.un.org/unsd/demographic/products/socind/education.htm'). GDP was collected from the [World Bank](http://data.worldbank.org/indicator/NY.GDP.MKTP.CD) and stored in the following file,  [API_NY.GDP.MKTP.CD_DS2_en_csv_v2.csv.](https://raw.githubusercontent.com/silkaitis/WealthEducation/master/API_NY.GDP.MKTP.CD_DS2_en_csv_v2.csv).  Logarithmic transforms were applied to scale the school life and GDP data.

**Results**

```
OLS Regression Results                            
==============================================================================
Dep. Variable:                      y   R-squared:                       0.191
Model:                            OLS   Adj. R-squared:                  0.185
Method:                 Least Squares   F-statistic:                     34.13
Date:                Mon, 03 Oct 2016   Prob (F-statistic):           3.26e-08
Time:                        19:17:47   Log-Likelihood:                -327.45
No. Observations:                 147   AIC:                             658.9
Df Residuals:                     145   BIC:                             664.9
Df Model:                           1                                         
Covariance Type:            nonrobust                                         
==============================================================================
                 coef    std err          t      P>|t|      [95.0% Conf. Int.]
------------------------------------------------------------------------------
const         13.9179      1.706      8.157      0.000        10.545    17.290
x1             3.9815      0.681      5.842      0.000         2.635     5.328
==============================================================================
Omnibus:                        4.935   Durbin-Watson:                   2.170
Prob(Omnibus):                  0.085   Jarque-Bera (JB):                4.436
Skew:                          -0.395   Prob(JB):                        0.109
Kurtosis:                       3.317   Cond. No.                         26.5
==============================================================================
```

![alt text](https://raw.githubusercontent.com/silkaitis/WealthEducation/master/School%20Life%20vs%20GDP.png)

**Interpretation**

The linear model has an R-squared of 19% indicating a weak to non-existent correlation between school life and GDP. There are a number of explanations for the lack of
predictive power. First, there are several variables not considered in this analysis that could improve the model such as number of students enrolled, level of education provided, and highest degree available. These variables could provide a more complete picture of the education system within each country. Second, GDP may not be proportional to the dollars spend on education within a country. Actual education spend would be more direct feature to predict school life.  Third, dollars spent within one country may not be as effective at increasing school life compared to another country.  A 'dollar effectiveness' metric could be used as an additional dimension for education spend.  Lastly, School life and GDP are most likely not constant year to year and any trends were not accounted for in this analysis.

In summary, additional data and research is needed to better predict school life.  

**Code**

* WealthEducation.ipynb ~ Analysis of School Life & GDP Data
