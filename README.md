# SQLAlchemy Challenge - Surfs Up!

![surfs-up.png](Images/surfs-up.png)

# Summary
The data was retrieved from hawaii sqlite file. I used Pandas, Matplotlib and SQLAlchemy ORM queries to do basic climate analysis and data exploration of the climate database. Then, I designed Flask API based on the queries and used FLASK to create your routes with relevant climate data in each API. Detailed below:



## Step 1 - Climate Analysis and Exploration
 
 Use the provided [climate_starter](climate_starter.ipynb) and [hawaii.sqlite](Resources/hawaii.sqlite) files to complete climate analysis and data exploration. Use SQLAlchemy `create_engine` to connect to your sqlite database and `automap_base()` to reflect your tables into classes and save a reference to those classes called `Station` and `Measurement`.

## Precipitation Analysis and Station Analysis

Designed a query to retrieve the last 12 months of precipitation data. Selected the `date` and `prcp` values. Loaded the query results into a Pandas DataFrame and set the index to the date column. Sort the DataFrame values by `date`. Plotted the results using the DataFrame `plot` method and used Pandas to print the summary statistics for the precipitation data. Designed a query to calculate the total number of stations and find the most active stations and another query to retrieve the last 12 months of temperature observation data (tobs). Plotted the results as a histogram with `bins=12`.

- - -
## Step 2 - Climate App - Flask
### Routes

* `/`

  * Home page.

  * List all routes that are available.

* `/api/v1.0/precipitation`

  * Convert the query results to a Dictionary using `date` as the key and `prcp` as the value in a JSON representation of my dictionary

* `/api/v1.0/stations`

  * Return a JSON list of stations from the dataset.

* `/api/v1.0/tobs`
  * query for the dates and temperature observations from a year from the last data point and returned a JSON list of Temperature Observations (tobs) for the previous year.

* `/api/v1.0/<start>` and `/api/v1.0/<start>/<end>`

  * Return a JSON list of the minimum temperature, the average temperature, and the max temperature for a given start or start-end range.

  * When given the start only, calculate `TMIN`, `TAVG`, and `TMAX` for all dates greater than and equal to the start date.

  * When given the start and the end date, calculate the `TMIN`, `TAVG`, and `TMAX` for dates between the start and end date inclusive.