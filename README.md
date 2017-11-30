{
 "cells": [
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "# Weather and Red Light Violations\n",
    "\n",
    "## The Question\n",
    "\n",
    "We explored the data of red light violations in the last 3 years in Chicago with 3 assumptions:\n",
    "1. There are more violations during holidays;\n",
    "2. There are more violations after Cubs' win;\n",
    "3. Weather influences the number of violations.\n",
    "\n",
    "After close examination, we reject the first two but see a clear seasonal variation in the red light violations. We continued our research with a regression between the violation numbers and the temperature and precipitation. There is no significant relationship between the violation and precipitation, but with the temperature rising, the red light violation number will also increase.\n",
    "\n",
    "## Data\n",
    "\n",
    "### Red Light Violations\n",
    "\n",
    "We used the [red light violations data](https://data.cityofchicago.org/Transportation/Red-Light-Camera-Violations/spqx-js37/data) from the Chicago City Portal. It provides us with the ID and address of the red light cameras, the date of violations and also the number of violations during the last 3 years. \n",
    "\n",
    "We transformed the address of the cameras to zip-codes using ArcMAP for further analysis.\n",
    "\n",
    "### Weather\n",
    "\n",
    "We used the [weather underground API](https://www.wunderground.com/weather/api/) to inform us everyday temperature and precipitation in Chicago.\n",
    "\n",
    "## Investigation\n",
    "\n",
    "All analysis code for this project can be accessed [here]().\n",
    "\n",
    "### General analysis\n",
    "\n",
    "#### Violation number changes over time:\n",
    "\n",
    "* Red light violation by day for the last 3 years:\n",
    "\n",
    "![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/violation%20number%20by%20day.png?raw=true \"violation number by day\")\n",
    "\n",
    "* Red light violation by weekday:\n",
    "\n",
    "![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/violation%20number%20by%20weekday.png?raw=true \"violation number by weekday\")\n",
    "\n",
    "* Red light violation by month:\n",
    "\n",
    "![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/violation%20number%20by%20month.png?raw=true \"violation number by month\")\n",
    "\n",
    "#### Red light violation per camera per day:\n",
    "\n",
    "![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/violation%20number%20by%20zipcode.png?raw=true \"violation number by zipcode\")\n",
    "\n",
    "#### Camera number by day for the last 3 years:\n",
    "\n",
    "![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/camera%20number%20trend.png?raw=true \"Camera number for the last 3 years\")\n",
    "\n",
    "\n",
    "### Before and after Christmas\n",
    "\n",
    "\n",
    "### Before and after Cubs' win\n",
    "\n",
    "\n",
    "### Relationship between weather and red light violations\n",
    "\n",
    "Plots of temperature and average violation per camera per day:\n",
    "\n",
    "![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/violation%20temperature%20plots.png?raw=true \"temperature and violation\")\n",
    "\n",
    "Plots of precipitation and average violation per camera per day:\n",
    "\n",
    "![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/violation%20p%20plots.png?raw=true \"precipitation and violation\")\n",
    "\n",
    "The results are as followed:\n",
    "\n",
    "**Model: ** |**R-squared: **| **Adj. R-squared:**\t| **F-statistic:\t**|**No. Observations:**\n",
    "--- | --- | --- | --- | --- \n",
    "Least Squares\t|0.134\t| 0.133\t| 70.89\t| 913\t\n",
    "\t\n",
    "\n",
    "**variable **| **coef**\t| **std err\t**|** t**\t| **P>[t]**\t| **[0.025**\t| **0.975]**\n",
    "--- | --- | --- | --- | --- | --- | ---\n",
    "Intercept\t| 1219.9670\t| 19.186\t| 63.585\t| 0.000\t| 1182.312\t| 1257.622\n",
    "temprature\t| 3.6908\t| 0.313\t| 11.775\t| 0.000\t| 3.076\t| 4.306\n",
    "precipitation\t| 49.1304\t| 522.450\t| 0.094\t| 0.925\t| -976.212\t| 1074.473\n",
    "\n",
    "![alt text](https://github.com/yzhang178/Final-Project/blob/master/images/relationship%20between%20temperature%20and%20violation.png?raw=true \"regression\")\n",
    "\n",
    "## Conclusions\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": []
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.6.2"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 2
}
