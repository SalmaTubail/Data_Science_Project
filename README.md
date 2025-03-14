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
1. Identify the most infulential weather conditions regarding flight delays
2. Develop predictive models to predict delay probabilities based on weather forecasts
3. Compare how different airlines and airports handle similar weather conditions
4. Analyze seasonal patterns in weather-related delays
5. Identify the most delay-prone airports, routes, and carriers
Analyze seasonal and diurnal patterns in delays
Visualize relationships between weather variables and delay durations

Calculate correlations between specific weather conditions and delay types
Perform hypothesis testing to validate relationships
Identify threshold values in weather parameters that significantly increase delay probabilities


Create classification models for delay risk categories (minimal, moderate, severe)
Evaluate model performance using appropriate metrics


Deliverables

Interactive dashboard visualizing key findings
Report detailing significant weather-delay relationships
Predictive tools for estimating delay risks based on weather conditions
Recommendations for travelers on best times/seasons to minimize weather-related delays

## Data 

### Primary Dataset: US Flight Delay and Cancellation Data
**Source**: [Flight Delays and Cancellations on Kaggle](https://www.kaggle.com/datasets/usdot/flight-delays)

**Description**:
This dataset contains information on US domestic flights operated by large air carriers in 2015, including:
- 5.8 million flight records
- Covers all major US airports and carriers
- Comprehensive temporal coverage (full year of 2015)
- Consists of catageroical data such as and numerical data like
- The Dataset contains 40 columns

**Key Columns**:
- `YEAR`, `MONTH`, `DAY`, `DAY_OF_WEEK`: Flight date information
- `AIRLINE`, `FLIGHT_NUMBER`: Carrier identification
- `ORIGIN_AIRPORT`, `DESTINATION_AIRPORT`: Airport codes
- `SCHEDULED_DEPARTURE`, `DEPARTURE_TIME`, `DEPARTURE_DELAY`: Departure information
- `SCHEDULED_ARRIVAL`, `ARRIVAL_TIME`, `ARRIVAL_DELAY`: Arrival information
- `CANCELLED`, `CANCELLATION_REASON`: Cancellation details
- `AIR_SYSTEM_DELAY`, `SECURITY_DELAY`, `AIRLINE_DELAY`, `LATE_AIRCRAFT_DELAY`, `WEATHER_DELAY`: Categorized delay reasons
- `DISTANCE`: Flight distance in miles

**Collection Method**:
I will download the dataset directly from Kaggle, which sources this data from the U.S. Department of Transportation's Bureau of Transportation Statistics.

### Enrichment Dataset: NOAA Weather Data
**Source**: [Iowa Environmental Mesonet - ASOS Network](https://mesonet.agron.iastate.edu/request/download.phtml?network=ASOS)

**Description**:
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

**Collection Method**:
I will use the Iowa Environmental Mesonet's custom data downloader to retrieve weather observations for the top 30 busiest US airports for 2015. The data will be requested in CSV format and downloaded programmatically using Python requests library.

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

### Expected Outcomes:
1. A predictive model that can estimate delay probability based on weather conditions
2. Insights into which airports are most vulnerable to specific weather conditions
3. Recommendations for optimizing flight scheduling during adverse weather
4. Visual analysis of weather impact patterns across the US aviation network

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

