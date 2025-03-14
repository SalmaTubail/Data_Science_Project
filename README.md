# Data_Science_Project
# An Analysis of Flight Delays and Cancelations with Weather Conditions

## Project Overview
This project will explore how weather conditions affect flight delays and cancellations across US airports. I aim to develop predictive models to forecast unforeseen delays or cancellations in flights by examining flight peformance data including Schedualed departure time, actual departure time, reason for cacellation, etc... with detailed weather observations such as visibility, temperature, and wind speed. The purpose of this analysis is to highlight the correlations and patterns of the weather conditions which are most disruptive to air travel and identify how their effects vary by airport, airline, and season, to aid airlines and travelers in anticipating delays.

## Motivation
Fligh Delay and cancelation are common occurance that cause costly hinderance to both travelers and airlines. Everytime I hear of a flight cancellation it has always been due to "Bad Waether". Although there are several factors contibuting to flight delay weather remains the most prominent factor. By understanding the relationship between specific weather conditions and flight performance: 

1. Airlines could better anticipate and mitigate delays
2. Airports could optimize resource allocation during adverse weather
3. Create tools so that passengers could make more informed travel decisions
4. The industry could potentially reduce the economic impact of weather-related disruptions

## Objectives:
1. Identify the most delay-prone airports, routes, and carriers
2. Identify the least and most delay-prone airports
3. Find the most infulential weather conditions regarding flight delays
4. Compare how different airlines and airports handle similar weather conditions
5. Develop predictive models to estimate delay probabilities based on weather forecasts
6. Visualize relationships and correlations between weather variables and delay durations 
7. Analyze seasonal patterns in weather-related delays to make recommendations for best travel times for travelers.
  
## Data 

### Primary Dataset 

2015 Flight Delays and Cancellations

***Collection Method***:
I will download the dataset directly from Kaggle, which sources this data from the U.S. Department of Transportation's Bureau of Transportation Statistics.

Source: [Flight Delays and Cancellations on Kaggle](https://www.kaggle.com/datasets/usdot/flight-delays)

**Description**:

This dataset contains information on US domestic flights operated by large air carriers in 2015, including:
- 5.8 million flight records over a full year (2015)
- Flight dates, times, origins, and destinations
- Consists of numerical data, such as:
    - Flight distance
    - Actual departure and arrival times
    - Scheduled departure and arrival times
- Consists of catageroical data, such as:
    - Delay durations categorized by reason
    - Cancellation information and reasons
- The Dataset contains 40 columns

**Key Columns**:
- YEAR, MONTH, DAY: Date of flight
- DAY_OF_WEEK: Day of week (1-7)
- AIRLINE: Two-letter airline code
- FLIGHT_NUMBER: Flight number
- TAIL_NUMBER: Aircraft identifier
- ORIGIN_AIRPORT, DESTINATION_AIRPORT: Airport codes
- SCHEDULED_DEPARTURE, DEPARTURE_TIME: Scheduled and actual departure times
- DEPARTURE_DELAY: Minutes of departure delay
- SCHEDULED_ARRIVAL, ARRIVAL_TIME: Scheduled and actual arrival times
- ARRIVAL_DELAY: Minutes of arrival delay
- CANCELLED: Whether the flight was cancelled (1 = cancelled)
- CANCELLATION_REASON: Reason for cancellation (A = airline, B = weather, C = NAS, D = security)
- DIVERTED: Whether the flight was diverted
- AIR_TIME, DISTANCE: Flight duration and distance
  
### Enrichment Dataset: 

NOAA Weather Data

***Collection Method***:
I will use the Iowa Environmental Mesonet's custom data downloader to retrieve weather observations for the top 30 busiest US airports for 2015. The data will be requested in CSV format and downloaded programmatically using Python requests library.

Source: [Iowa Environmental Mesonet - ASOS Network](https://mesonet.agron.iastate.edu/request/download.phtml?network=ASOS)

**Description**:
We will enrich our flight data with weather information from the Iowa Environmental Mesonet - ASOS Network for the following reasons:

Weather observations come directly from airport weather stations, ensuring precise location matching
Data includes hourly observations, allowing for time-specific correlation with flights
Comprehensive weather variables that impact aviation operations
Programmatic access for efficient data collection
This dataset provides historical weather observations from Automated Surface Observing System (ASOS) stations located at airports across the United States, including:
- Hourly weather measurements
- Coverage for all major US airports
- Matches the time period of the flight dataset (2015)
  
**Key Columns**:
- `station`: Airport weather station identifier
- `valid`: Timestamp of weather observation
- `tmpf`: Temperature (Fahrenheit)
- `dwpf`: Dew point temperature (Fahrenheit)
- `relh`: Relative humidity (%)
- `drct`: Wind direction (degrees)
- `sknt`: Wind speed (knots)
- `p01i`: 1-hour precipitation (inches)
- `vsby`: Visibility (miles)
- `gust`: Wind gust (knots)
- `skyc1`, `skyc2`: Sky condition (cloud cover)
- `wxcodes`: Present weather codes
- `metar`: Raw METAR data (meteorological aerodrome report)

## Data Enhancement Strategy
The primary enhancement will involve merging flight and weather data through:

1. **Temporal Matching**: Connecting flight departure times with the closest weather observations
2. **Spatial Matching**: Linking airport codes (e.g., 'ORD' for Chicago O'Hare) with their corresponding weather station identifiers (e.g., 'KORD')
3. **Feature Engineering**: Creating derived features such as:
   - Weather severity indices
   - Seasonal indicators
   - Time-based features (peak travel hours, holidays)
   - Airport congestion metrics
4. **Additional Context**:
   - Adding airport geographical data (latitude/longitude)
   - Incorporating airport capacity information
   - Including holiday and special event indicators


## Implementation Timeline
- **By March 18**: Complete data collection, cleaning, and preliminary EDA
- **By April 23**: Implement machine learning models for delay prediction
- **By May 30**: Finalize analysis, prepare visualizations, and complete documentation

## limitations and Considerations
- Weather is just one factor among many that contribute to flight delays
- Historical patterns may not perfectly predict future performance due to climate change
- Airport infrastructure and airline policies regarding weather conditions vary
- Data quality issues may exist in both flight and weather datasets

## Future Work
- Expand the analysis to multiple years to identify long-term trends
- Incorporate real-time weather forecasting data for operational predictions
- Develop a web-based tool for delay risk assessment
- Include economic impact analysis of weather-related delays

## References
1. Bureau of Transportation Statistics. "Understanding the Reporting of Causes of Flight Delays and Cancellations."
2. Federal Aviation Administration. "Weather Delay Cost."
3. NOAA National Centers for Environmental Information. "Data Access."

