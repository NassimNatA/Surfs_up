# Surfs_up
## Overview of Analysis

The purpose of this analysis is to obtain the temperature data from of months of June and December in Oahu to determine what trends temperature are present for an opening surf shop. To do so, tools such as SQLite, SQLAlchemy, and Flask were used to analyze database structures and query statistics. 

## Results 

Two deliverables were produced in this project: 
- Deliverable 1: Summary Statistics for June
- Deliverable 2: Summary Statistics for December
Summary statistics were produced for each respective month by the following steps and code: 
- Created Measurement table to retrieve the temperatures for the month of June

`temp_june = []
temp_june = session.query(Measurement.date, Measurement.tobs).\
filter(extract('month', Measurement.date) == 6).all()
print(temp_june)`

- Converted the  temperatures to a list.


`list(temp_X)`

- Created a DataFrame from the list of temperatures for each month.  


`df_temp_X = pd.DataFrame(temp_X)
df_temp_X.head()`

- Created summary statistics for each month dataframe


`df_temp_X.describe()`

Three major points from the two deliverable summary statistics: 
- 
- 
