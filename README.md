# Weather and Red Light Violations

## The Question

We explored the data of red light violations in the last 3 years in Chicago with 3 assumptions:
1. There are more violations around holidays;
2. There are more violations after Cubs' win;
3. Weather influences the number of violations.

After close examination, we found slight evidence supporting the first two and see a clear seasonal variation in the red light violations. We then continued our research with a regression between the violation number and the temperature and precipitation. There is no significant relationship between the violation and precipitation, but with the temperature rising, the red light violation number will increase.

## Data

### Red Light Violations

We used the [red light violations data](https://data.cityofchicago.org/Transportation/Red-Light-Camera-Violations/spqx-js37/data) from the Chicago City Portal. It provides us with the ID and address of the red light cameras, the date of violations and also the number of violations during the last 3 years. 

We transformed the address of the cameras to zip-codes using ArcMAP for further analysis.

### Weather

We used the [weather underground API](https://www.wunderground.com/weather/api/) to inform us everyday temperature and precipitation in Chicago.

## Investigation

All analysis code for this project can be accessed [here](https://github.com/yzhang178/Final-Project/blob/master/Project.Lingfei%20FINAL.ipynb).

### General analysis

#### Violation number changes over time:

* Red light violation by day for the last 3 years:

We can see an overall upward trend and a clear seasonal variation in the daily red light violation number. People tend to violate the red lights in warm days.

![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/violation%20number%20by%20day.png?raw=true "violation number by day")

* Red light violation by weekday:

The violations spread almost evenly among the weekdays with a small peak around the weekend. A possible explanation might be people drive more at weekends.

![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/violation%20number%20by%20weekday.png?raw=true "violation number by weekday")

* Red light violation by month:

This gives us further support on the seasonal variation we obersed from the first graph. The peak appears at July to September. 

![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/violation%20number%20by%20month.png?raw=true "violation number by month")

#### Red light violation per camera per day by zip-code:

We think the violation number per camera per day could give us a more sensible illustration on the regional driving behavior. The graph gives us two outliers: 60657 and 60804. However, we can hardly find the reasons why the average numbers are high in those two areas. Further analysis is required.

![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/violation%20number%20by%20zipcode.png?raw=true "violation number by zipcode")

#### Camera number by day for the last 3 years:



![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/camera%20number%20trend.png?raw=true "Camera number for the last 3 years")


### Before and after Christmas

![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/christmas%20bar.png?raw=true "Christmas")

### Before and after Cubs' win

![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/cubs%20bar.png?raw=true "Christmas")

### Relationship between weather and red light violations

Plots of temperature and average violation per camera per day:

![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/violation%20temperature%20plots.png?raw=true "temperature and violation")

Plots of precipitation and average violation per camera per day:

![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/violation%20p%20plots.png?raw=true "precipitation and violation")

The results are as followed:

**Model: ** |**R-squared: **| **Adj. R-squared:**	| **F-statistic:	**|**No. Observations:**
--- | --- | --- | --- | --- 
Least Squares	|0.134	| 0.133	| 70.89	| 913	
	

**variable **| **coef**	| **std err	**|** t**	| **P>[t]**	| **[0.025**	| **0.975]**
--- | --- | --- | --- | --- | --- | ---
Intercept	| 1219.9670	| 19.186	| 63.585	| 0.000	| 1182.312	| 1257.622
temprature	| 3.6908	| 0.313	| 11.775	| 0.000	| 3.076	| 4.306
precipitation	| 49.1304	| 522.450	| 0.094	| 0.925	| -976.212	| 1074.473

![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/relationship%20between%20temperature%20and%20violation.png?raw=true "regression")

## Conclusions

