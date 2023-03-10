# sqlalchemy-challenge
Module 10 challenge

This assignment is performed using sqlalchemy to query and analyze climate data, and using Flask to deliver local host query results to web browser.

###Step 1 - Climate Analysis and Exploration

To begin, I used:
- Python and SQLAlchemy to do basic climate analysis and data exploration of your climate database. All of the following analysis should be completed using SQLAlchemy ORM queries, Pandas, and Matplotlib.

- Provided starter notebook and hawaii.sqlite files to complete the climate analysis and data exploration.

- SQLAlchemy create_engine to connect to your sqlite database.

- SQLAlchemy automap_base() to reflect your tables into classes and save a reference to those classes called Station and Measurement.

I linked Python to the database by creating an SQLAlchemy session.

##Precipitation Analysis

Start by finding the most recent date in the data set.
Using this date, I retrieved the last 12 months of precipitation data by querying the 12 preceding months of data. 
Selected only the date and prcp values.
Loaded the query results into a Pandas DataFrame and set the index to the date column.
Sorted the DataFrame values by date.
Plotted the results using the DataFrame plot method.
Used Pandas to print the summary statistics for the precipitation data.

##Station Analysis

Designed a query to calculate the total number of stations in the dataset.
Designed a query to find the most active stations (i.e. which stations have the most rows?).
Listed the stations and observation counts in descending order.
Found out which station id has the highest number of observations?
Using the most active station id, calculated the lowest, highest, and average temperature.
Designed a query to retrieve the last 12 months of temperature observation data (TOBS).
Filtered by the station with the highest number of observations.
Queried the last 12 months of temperature observation data for this station.
Plotted the results as a histogram with bins=12.
Closed out your session.

###Step 2 - Climate App

After completing the initial analysis, designed a Flask API based on the queries I developed. Usde Flask to create routes.

Routes

/ - Home page.
Listed all routes that are available.

/api/v1.0/precipitation - Converted the query results to a dictionary using date as the key and prcp as the value.
Returned the JSON representation of your dictionary.

/api/v1.0/stations - Returned a JSON list of stations from the dataset.

/api/v1.0/tobs - Queried the dates and temperature observations of the most active station for the last year of data.
Return a JSON list of temperature observations (TOBS) for the previous year.

/api/v1.0/ and /api/v1.0// - Return a JSON list of the minimum temperature, the average temperature, and the max temperature for a given start or start-end range.

When given the start only, calculate TMIN, TAVG, and TMAX for all dates greater than and equal to the start date.

When given the start and the end date, calculate the TMIN, TAVG, and TMAX for dates between the start and end date inclusive.
