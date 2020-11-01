# Surfs_up
## Overview of Analysis

The purpose of this analysis is to obtain the temperature data from of months of June and December in Oahu to determine what trends temperature are present for an opening surf shop. To do so, tools such as SQLite, SQLAlchemy, and Flask were used to analyze database structures and query statistics. 

## Results 

Two deliverables were produced in this project: 
- Deliverable 1: Summary Statistics for June
- Deliverable 2: Summary Statistics for December
Summary statistics were produced for each respective month by the following steps and code: 
- Created Measurement table to retrieve the temperatures for the month of June:

`temp_june = []`
`temp_june = session.query(Measurement.date, Measurement.tobs).\
`filter(extract('month', Measurement.date) == 6).all()`
`print(temp_june)`

- Converted the  temperatures to a list:
`list(temp_X)`

- Created a DataFrame from the list of temperatures for each month: 
`df_temp_X = pd.DataFrame(temp_X)`
`df_temp_X.head()`

- Created summary statistics for each month dataframe:
`df_temp_X.describe()`

Three major points from the two summary statistics deliverables: 
- The mean temperature for June is higher at 74.9 degrees F, compared to the December mean of 71.0 degrees F. 
- The month of June had a min temperautre of 64.0 F, and a maximum temperature of 85.0 F
- The month of December had a min tempearture of 56.0 F , and a maximum temperature of 83.0 F

## Summary
Overall, the results above demonstrate that temperature trends in Oahu are favorable for the surfs up business to proceed with ice cream sales. Despite differing in the min and max temperatures, both June and December have mean tempearturs in the 70s that which will be economical for sales. Two additional queries to gather more weather information about the precipitation rates from the months of June and December are the following: 
1. Perform a query to retrieve the data and precipitation scores: 
`results = []`
`results = session.query(Measurement.date, Measurement.prcp).filter(Measurement.date >= prev_year).all()`

2. Saves results as a dataframe, set the index to the date column, sort the dataframe by date, and use Pandas Plotting with Matplotlib to plot the data: 
`df = pd.DataFrame(results, columns=['date','precipitation'])`
`df.set_index(df['date'], inplace=True)`
`df.plot()`

The graphs produced from above will give more insight on rainfall trends which can further help forecast appropriate months for sales. 
