# PyBer Analysis Report

## Background and Results

### Purpose
  The purpose of this analysis was to find the key metrics of the ride-sharing data by city type, as well as determining the total fares for each week by city type in the year 2019. The analysis was conducted using Python 3.6.1 and Jupyter Notebook 6.0.3. The data from the city_data.csv and ride_data.csv were merged together and then used to determine the total rides, total drivers, total fares, average fare per ride and average fare per driver for each city type (Urban, Suburban or Rural). To find the total rides/drivers/fares, the groupby function was used. Shown below is an example of the code used to calculate the sum of fares for each city type:
  ```
  total_fares_by_type = pyber_data_df.groupby(["type"]).sum()["fare"]
  ```
  The average fare per ride/driver was then caluclated by dividing the total fares per city type by the total rides or drivers, respectively. 
### Technical Analysis

### Results

### Summary

## Challenges Encountered and Overcome

### Challenges and Difficulties Encountered

* Programming

* Data analysis

* Graphing, etc

### Technical Analyses Used

## Recommendations and Next Steps

### Recommendations for Future Analysis

### Additional Analysis 1

* Description of Approach

* Technical Steps

### Additional Analysis 2

* Description of Approach

* Technical Steps
