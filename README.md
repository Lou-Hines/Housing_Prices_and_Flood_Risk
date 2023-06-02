

# King_County_Flood_Risk

Want to buy a home in King County? Are you at risk for flooding? How will your home hold value in a flood? Lets find out.
## Problem statement

As a data scientist, I have been tasked with helping middle-income home buyers purchase a home that will have minimal flood damage. The buyers are focused on the retention of the home value over time, how it will change, and how the risk of flooding will diminish their home assets.
To do this I looked at:
1.  How do flood scores affect home prices?
2. Which house attributes increase the sale price?
3. Will a change in sea level creating new waterfront properties affect home value?
# Components
* **Jupyter Notebook**
The Jupyter Notebooks (https://github.com/Lou-Hines/Housing_Prices_and_Flood_Risk/blob/main/Final_Notebook-Cleaning_and_EDA.ipynb)  and 
(https://github.com/Lou-Hines/Housing_Prices_and_Flood_Risk/blob/main/Final_Notebook-Merged_Data_Cleaning_and_Modelling.ipynb) are our key deliverables and contains details of our approach and methodology, data cleaning, exploratory data analysis, and model building and validation.
* **Presentation**
The [presentation](https://github.com/Lou-Hines/Housing_Prices_and_Flood_Risk/blob/main/Presentation-Flooding_and_Homebuying_KC.pdf) gives an overview of the findings of the data and recommendations of which homes to purchase.  It is aimed to be between 5  long.
## Technologies/ Packages
* Python
* Matplotlib
* Seaborn
* Pandas
* Numpy
* Statsmodels
* Scikit-learn
* Geopandas
* Geopy
* Reverse_geocoder

### The Data

This project uses the King County House Sales dataset, which can be found in  `kc_house_data.csv` in the data folder in this assignment's GitHub repository. The description of the column names can be found in `column_names.md` in the same folder. We also used data from FEMA's National Flood Insurance Program (NFIP) sourced from Kaggle, which can likewise be found under the NFIP folder within the data folder.

The features we primarily looked in determining price included:

* `neighborhoods (sourced from latitude and longitude columns)`
* `yr_renovated
* `zipcode`
* `area flood score min'
* `area flood score max`
* `avg area flood score`

### Working with the Data

We cleaned our data by looking at multicollinearity; we also checked for null values and removed outliers. We ran VIF scores, homescedascity models, RMSE, and looked
for normal distributions of key features. We ran regressions on numerous features to determine patterns and improve the predictability of our model. We experimented with log transforms of sales data but found no effect. We likewise found little effect of flood score on determining price. We utilized histograms, heatmaps, linear
regression visualizations, and more. Through all this, we determined that the strongest feature by far was "neighborhood" and
by further modelling against recent renovations (2010 onward), we acheived our highest R2, though there was still some evidence of multicollinearity. Part of this
is due to the strong correlation between our various flood score columns. 

We are confident that our final model - with an R2 of ~76% - is  solid in predicting price.. Our test and train models were closely aligned.

### Results

Neighborhoods are highly associated with sales price; much more so than zipcodes, cities, etc. Onehot encoding the neighborhood feature gave us our highest
model boost. 

Recent renovation onehot encoding also gave us a slight boost.

Therefore, we assert that selecting by neighborhood and recent renovation status are two key features in determining sales price.

Even though flood scores (scores we created ourselves based on FEMA's categories) did not correspond with sales price, we decided to sort our results by these scores
taking into account neighborhoods, above-average sales prices, and recent renovations. We returned the neighborhoods that had the best combination of these features, 
with a flood score less than 2. 






## Summary

Working with two datasets, and creating our own in-house scoring system, we determined the best neighborhoods for middle-high income homebuyers in King County who are concerned about flooding due to climate change. Going forward, we would like to update our data based on more contemporary actuarial data.


* If you have any questions, you can contact me at hinesmeghan1@gmail.com or https://www.linkedin.com/in/meg-hines-data-scientist/. Please note that "Lou" is my 
* chosen name.
