# PyBer Analysis Report

## Purpose, Technical Analysis and Results
   
   The purpose of this analysis was to find the key metrics of the ride-sharing data by city type, as well as determining the total fares for each week by city type in the year 2019. The analysis was conducted using Python 3.6.1 and Jupyter Notebook 6.0.3. The data from the city_data.csv and ride_data.csv were merged together and then used to determine the total rides, total drivers, total fares, average fare per ride and average fare per driver for each city type (Urban, Suburban or Rural). To find the total rides/drivers/fares, the groupby function was used. Shown below is an example of the code used to calculate the sum of fares for each city type:
   ```
   total_fares_by_type = pyber_data_df.groupby(["type"]).sum()["fare"]
   ```
   The average fare per ride/driver was then caluclated by dividing the total fares per city type by the total rides or drivers, respectively. This data was then combined into a new summary data frame. 
![Summary DF](https://github.com/oshadiw/PyBer_Analysis/blob/master/analysis/Summary%20DF.png) 

This table shows that the total rides, drivers and fares were much higher in Urban cities compared to Suburban and Rural cities. Rural cities, however, had higher average fares per ride and driver compared to the other two city types. 
  
  In order to find the total fares for each week by city type, a new data frame was created using only the Date, City Type and Fare metrics. The Date column wsa converted to datatime format using the following code:
  ```
  pyber_fares_df["Date"]=pd.to_datetime(pyber_fares_df["Date"])
  ```
  The data within the year 2019 was selected using the .loc method, and a new data frame was created and used to generate a FiveThirtyEight style line chart. 
![Line Chart](https://github.com/oshadiw/PyBer_Analysis/blob/master/analysis/ChallengeFig.png)

This figure shows various trends between the three city types. For example, all three city types had a peak in total fare towards the end of February. The Urban fares seemed to gradually increase thorughout the year, with some drops but never down to the starting value. Rural cities had low fares thorughout the year (compared to the other city types), never going above $500. 

## Challenges Encountered and Overcome

* Data analysis
   - One challenge encountered during the analysis was coming up with descriptive names for the multiple data frames created with the same info (Date, City Type, Fare) but changing the formatting and order of the columns. In order to overcome this, I tried to keep the names as descriptive as possible, using names that noted what terms were being highlighted in the new data frame. 

* Programming
   - Another challenge that I faced was the summary data frame not splitting the values by city type. After rewriting the code numerous times, I realized that there was an extra set of brackets when creating the data frame. Once that bracked set was deleted, the data frame ran correctly. 

## Recommendations for Future Analysis

In order to address any disparities among city types, I would recommend that a rides-per-capita metric be calulated, as well as using a wider range of dates to view the total fares over time. 

### Additional Analysis 1

* A valuable dataset to have would be the total population of the cities and to use those values to caluclate the total rides per capita. 

* To perform this analysis, the sum of the population of cities would be caluclated using the groupby method, and then the total ride values would be divided by the population count. This would give the company a more accurate depiction of how useful it is to have Pyber rides offered in certain cities. If the rides per capita is below a certain value, then it might not be worth the operating costs to have Pyber in those cities. 

### Additional Analysis 2

* To see if there are certain trends based on total fare, depending on the time of year, a wider range of dates should be used.

* The same graph that was previously used could be created, using the FiveThirtyEight style. The graph could be formatted in a way to show the total fare by city type over the course of a year, with multiple years. This way, the company could determine whether cetain months have a higher total fare and subsequently charge more or less. This could yield a higher profitability to the company, as well as encourage riders to travel more during times when the fare is lower. 
