 # Weather and Red Light Violations

## The Question

We explored the data of red light violations in the last 3 years in Chicago with 2 assumptions:
1. There are more violations around Christmas;
2. Weather influences the number of violations.

After close examination, we reject the first, and see a clear seasonal variation in the number of violations. We then continued our research with a regression between the violation number and the temperature and precipitation. There is no significant relationship between the violation and precipitation, but with the temperature rising, the red light violation number will increase.

## Data

### Red Light Violations

We used the [red light violations data](https://data.cityofchicago.org/Transportation/Red-Light-Camera-Violations/spqx-js37/data) from the Chicago City Portal. It provides us with the ID and address of the red light cameras, the date of violations and also the number of violations during the last 3 years. 

We transformed the address of the cameras to zip-codes using ArcMAP for further analysis.

### Weather

We used the [weather underground API](https://www.wunderground.com/weather/api/) to inform us everyday temperature and precipitation in Chicago.

## Investigation

All analysis code for this project can be accessed [here](https://github.com/yzhang178/Final-Project/blob/master/Data%20Analysis.ipynb).

### General analysis

#### Violation number changes over time:

* Red light violation by day for the last 3 years:

We can see an overall upward trend and a clear seasonal variation in the daily red light violation number. People tend to violate the red lights in warm days.

![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/violation%20number%20by%20day.png?raw=true "violation number by day")

* Red light violation by weekday:

The violations spread almost evenly among the weekdays with a small peak around the weekend. A possible explanation might be people drive more at weekends.

![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/violation%20number%20by%20weekday.png?raw=true "violation number by weekday")

* Red light violation by month:

This gives us further support on the seasonal variation we obersed from the first graph. The peak appears from July to September. 

![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/violation%20number%20by%20month.png?raw=true "violation number by month")

#### Red light violation per camera per day by zip-code:

We think the violation number per camera per day could give us a more sensible illustration on the regional driving behavior. The graph shows us two outliers: 60657 and 60804. However, we can hardly find the reasons why the average numbers are high in those two areas. Further analysis is required.

![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/violation%20number%20by%20zipcode.png?raw=true "violation number by zipcode")


### Before and after Christmas

After playing with the data more generally, we started to test our assumptions. Firstly, we looked at the violation number during the Christmas week (12.20-12.27) in the last 3 years. No significant changes happened around the holiday but we can observe a clear decline on the exact Christmas Day 12.25. We think that's because people usually stay with their family and drive less on that day.

![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/christmas%20bar.png?raw=true "Christmas")

### Relationship between weather and red light violations

Inspired by the seasonal difference of the violation number and Jamie's weather and crime study, we decide to continue our research and explore the relationship between the weather and the red light violations.

Firstly, we drew two plot graphs to have a general idea about the data. We observed a positive relationship between temperature and violations but no obvious link between precipitation and violations.

Plots of temperature and average violation per camera per day:

![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/violation%20temperature%20plots.png?raw=true "temperature and violation")

Plots of precipitation and average violation per camera per day:

![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/violation%20p%20plots.png?raw=true "precipitation and violation")

Then we ran a multivariable regression to test the statistical relationship between the average red light violation per camera per day and the temperature and precipitation. Quite similar to our prompt observation, the regression results are as followed:

**Model: ** |**R-squared: **| **Adj. R-squared:**	|**No. Observations:**
--- | --- | --- | --- 
OLS	|0.323	| 0.321		| 914	
	

**variable **| **coef**	| **std err	**|** t**	| **P>[t]**	| **[0.025**	| **0.975]**
--- | --- | --- | --- | --- | --- | ---
Intercept	| 3.7480	| 0.093	| 40.387	| 0.000	| 3.566	| 3.930
temprature	| 0.0340	| 0.002	| 20.711	| 0.000	| 0.031	| 0.037
precipitation	| -3.6668	| 1.688	| -2.172	| 0.030	| -6.980	| -0.354


When the temperature increases by 1 degree, the average red light violation per camera per day will increase by 0.034.

![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/relationship%20between%20temperature%20and%20violation.png?raw=true "regression")

## Conclusions

Our three assumptions have been tested: 1) we can see no obvious change of red light violations around Christmas, except for a decline on the Christmas Day; 2) people make red light violations more in warm days and when the temperature increases by 1 degree, the average red light violation per camera per day will increase by 0.034.

Further analysis is required in: 1) why the violation per camera per day is extremely high in zip-code 60657 and 60804; 2) if the overall increase in violation is caused by people's increasingly impertinent driving behavior or a more reasonable geographical setup of the cameras.
