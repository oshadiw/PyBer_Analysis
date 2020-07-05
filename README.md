# PyBer Analysis Report

## Background and Results

### Purpose, Technical Analysis and Results
   
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
  The data within the year 2019 was selected using the .loc method, and a new data frame was created and used to create a FiveThirtyEight style line chart. 
![Line Chart](https://github.com/oshadiw/PyBer_Analysis/blob/master/analysis/ChallengeFig.png)

This figure shows various trends between the three city types. For example, all three city types had a peak in total fare towards the end of February. The Urban fares seemed to gradually increase thorughout the year, with some drops but never down to the starting value. Rural cities had low fares thorughout the year (compared to the other city types), never going above $500. 

## Challenges Encountered and Overcome

* Programming

* Data analysis

* Graphing, etc


### Recommendations for Future Analysis

### Additional Analysis 1

* Description of Approach

* Technical Steps

### Additional Analysis 2

* Description of Approach

* Technical Steps
