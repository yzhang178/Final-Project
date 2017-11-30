# Weather and Red Light Violations

## The Question

We explored the data of red light violations in the last 3 years in Chicago with 3 assumptions:
1. There are more violations during holidays;
2. There are more violations after Cubs' win;
3. Weather influences the number of violations.

After close examination, we reject the first two but see a clear seasonal variation in the red light violations. We continued our research with a regression between the violation numbers and the temperature and precipitation. There is no significant relationship between the violation and precipitation, but with the temperature rising, the red light violation number will also increase.

## Data

### Red Light Violations

We used the [red light violations data](https://data.cityofchicago.org/Transportation/Red-Light-Camera-Violations/spqx-js37/data) from the Chicago City Portal. It provides us with the ID and address of the red light cameras, the date of violations and also the number of violations during the last 3 years. 

We transformed the address of the cameras to zip-codes using ArcMAP for further analysis.

### Weather

We used the [weather underground API](https://www.wunderground.com/weather/api/) to inform us everyday temperature and precipitation in Chicago.

## Investigation

All analysis code for this project can be accessed [here]().

### General analysis

#### Violation number changes over time:

* Red light violation by day for the last 3 years:

![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/violation%20number%20by%20day.png?raw=true "violation number by day")

* Red light violation by weekday:

![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/violation%20number%20by%20weekday.png?raw=true "violation number by weekday")

* Red light violation by month:

![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/violation%20number%20by%20month.png?raw=true "violation number by month")

#### Red light violation per camera per day:

![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/violation%20number%20by%20zipcode.png?raw=true "violation number by zipcode")

#### Camera number by day for the last 3 years:

![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/camera%20number%20trend.png?raw=true "Camera number for the last 3 years")


### Before and after Chris


### Before and after Cubs' win


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
