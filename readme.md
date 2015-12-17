# Final Project

##### Graham Bullard
##### December 16, 2015
##### CSC 570

[Project Notebook](https://github.com/gbullard/Project/blob/master/Project.ipynb)

As populations continue to grow, fresh water is becomming an increasingly important public resource.  Futhermore, as the western United States continues to face drought, the ability for local leaders to accurately project changes to fresh water consumption is crucial. The United States Geological Survey maintains data on the industrial, agricultural, and domestic water usage for every county in the country.  Using this data (compiled in 2010), we should be able to determine which industries have the largest impact on a counties' usage and make some predictions about how consumption rates might change if businesses or population expand.

The initial attempt to discover which industries will impact a county's fresh water consumption (using a random forest) is a little cluttered, as the USGS's dataset initially measured 117 attributes.  An inspection of the data shows that roughly half of attributes track usage of salt water (sailine), and are not needed for predicting fresh water usage. Further, viewing the attribute titles sorted by importance after using the random forest shows that there are redundancies in the attributes that track each industries' consumption.  To account for this, the features are reduced to the best predictive attribute of each industrial category:  public supply, domestic, irrigation, livestock, aquaculture, industrial, mining, and thermoelectric power water use, as well as public supply for domestic use.

<figure>
  <img src="http://i.imgur.com/hewtQEs.png" alt="Feature Graph" width="778" height="317">
</figure>

### Most Important Features:
* Total population of county, in thousands
* Public Supply, total withdrawals, fresh, in Mgal/d
* County FIPS code
* Livestock, total withdrawals, fresh, in Mgal/d
* Irrigation, acres irrigated, sprinkler, in thousands
* Mining, total withdrawals, fresh, in Mgal/d
* Industrial, self-supplied total withdrawals, fresh, in Mgal/d
* Aquaculture, total withdrawals, fresh, in Mgal/d
* Thermoelectric, power generated, in gigawatt-hours

### Conclusion:
* Domestic use of fresh water is a better predictor of total consumption than any specific industry. 
* General information, such as total population, about a county also serves as a very good predictor. 
* Water usage varies greatly by geographic location, as different counties recieve different rainfall totals, and generally posses different patterns of water usage. 
* We can deduce more about a county's total water usage based upon agricultural water consumption (both livestock and irrigation) than any other industry. 
* Whether water is used once, or recirculated, water usage in power generation makes little impace on total usage.
* While irrigation generally makes a large impact on usage, irrigation of golf courses makes a much smaller impact as it is heavily supplimented by surface water (rain supply).

### Source
   U.S. Geological Survey - Estimated Use of Water in the United States
County-Level Data for 2010 [[Link](http://water.usgs.gov/watuse/data/2010/)]
