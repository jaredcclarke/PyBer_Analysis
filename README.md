# PyBer_Analysis
## Overview
The purpose of this analysis was to create a summary of the provided ride-sharing data by city type (i.e. Urban, Suburban, and Rural). A multiple line graph was created from the summary data to illustate the the total weekly fares for each city type. 

### Resources
* Python version 3.7.7
* Anaconda 4.8.5
* Pandas
* Jupyter Notebook 6.1.4
* "Resources/city_data.csv"
* "Resources/ride_data.csv"

## Results
### Ride-Sharing Data
* First needed to find out the total rides for each city, total drivers for each city type, and the average fare per ride for each city type:
```type_of_rides_count = pyber_data_df.groupby(['type']).count()['ride_id']
    type_of_rides_count 
```

![](https://github.com/jaredcclarke/PyBer_Analysis/blob/main/Resources/ride_count.png)

![](https://github.com/jaredcclarke/PyBer_Analysis/blob/main/Resources/Steps_2_to_4.png)

* After the average fare per driver for each city type was calcuated, a summary DataFrame was created to showcase the data:
![](https://github.com/jaredcclarke/PyBer_Analysis/blob/main/Resources/Steps_5_to_7.png)

### Multiple Line Plot
* Created a new Dataframe to show the sum of fares:
```date_counts = pyber_data_df.groupby(['type', 'date']).sum()['fare']
date_counts 
```
* Then the index on the DataFrame was reset and susequently created a pivot table with date as the index, columns as the city type and values as the fare. Specified the date range of 01/01/2019 through 04/29/2019. Then the index was set to datetime datatype:

![](https://github.com/jaredcclarke/PyBer_Analysis/blob/main/Resources/pivot_loc.png)

![](https://github.com/jaredcclarke/PyBer_Analysis/blob/main/Resources/pivot_df.png)

![](https://github.com/jaredcclarke/PyBer_Analysis/blob/main/Resources/jan_to_apr.png)

* The datatype was checked and then created a new DataFrame with the `resample()` function. This grouped the data the by weeks:

![](https://github.com/jaredcclarke/PyBer_Analysis/blob/main/Resources/weekly_fare.png)

* The total of all fares for each city type, from 01/01/2019 through 04/29/2019, summarized in the following multiple line graph:
![](https://github.com/jaredcclarke/PyBer_Analysis/blob/main/analysis/PyBer_fare_summary.png)
## Summary
The following information can be summarized from the data analysis:
* The largest total fares come from urban cities and the lowest come from rural cities
* The largest total fares for urban and suburban cities took place towards the end of February.
* Largest total fares for rural cities took place in the start of April. 

## Recommendations
* PyBer could increase prices for Urban cities for more revenue
* PyBer could decrease fares for suburban and rural cities to increase ride-shares.
* PyBer could increase number of cars in the rural and suburban cities.

