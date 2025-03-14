# Data_Science_Project
# Flight Delay Analysis with Weather Conditions

## Project Overview
This project aims to analyze how weather conditions impact flight delays and cancellations across US airports. By combining comprehensive flight data with detailed weather observations, the project will develop predictive models to forecast potential delays based on weather patterns and other operational factors. The analysis will identify which weather conditions are most disruptive to air travel and how these impacts vary across different airports, airlines, and seasons.

## Motivation
I chose this project because of its significant real-world applications in the aviation industry. Flight delays cost airlines and passengers billions of dollars annually, and weather is responsible for approximately 70% of all delays. By understanding the relationship between specific weather conditions and flight performance:

1. Airlines could better anticipate and mitigate delays
2. Airports could optimize resource allocation during adverse weather
3. Passengers could make more informed travel decisions
4. The industry could potentially reduce the economic impact of weather-related disruptions

As an engineering student interested in transportation systems and data science, this project allows me to apply machine learning techniques to solve a complex problem with multiple variables and stakeholders.

## Data Sources

### Primary Dataset: US Flight Delay and Cancellation Data
**Source**: [Flight Delays and Cancellations on Kaggle](https://www.kaggle.com/datasets/usdot/flight-delays)

**Description**:
This dataset contains information on US domestic flights operated by large air carriers in 2015, including:
- 5.8 million flight records
- Covers all major US airports and carriers
- Comprehensive temporal coverage (full year of 2015)

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

## Project Objectives

### Primary Objectives:
1. Identify which specific weather conditions have the greatest impact on flight delays
2. Develop predictive models to forecast delay probabilities based on weather forecasts
3. Compare how different airlines and airports handle similar weather conditions
4. Analyze seasonal patterns in weather-related delays

### Technical Objectives:
1. Apply time series analysis to identify patterns and anomalies
2. Implement multiple machine learning algorithms (Random Forest, Gradient Boosting, Neural Networks) for delay prediction
3. Develop interactive visualizations showing the relationship between weather variables and delay metrics
4. Create a delay risk scoring system for different weather scenarios

### Expected Outcomes:
1. A predictive model that can estimate delay probability based on weather conditions
2. Insights into which airports are most vulnerable to specific weather conditions
3. Recommendations for optimizing flight scheduling during adverse weather
4. Visual analysis of weather impact patterns across the US aviation network

## Implementation Timeline
- **By March 18**: Complete data collection, cleaning, and preliminary EDA
- **By April 23**: Implement machine learning models for delay prediction
- **By May 30**: Finalize analysis, prepare visualizations, and complete documentation

## Future Work
- Expand the analysis to multiple years to identify long-term trends
- Incorporate real-time weather forecasting data for operational predictions
- Develop a web-based tool for delay risk assessment
- Include economic impact analysis of weather-related delays

## References
1. Bureau of Transportation Statistics. "Understanding the Reporting of Causes of Flight Delays and Cancellations."
2. Federal Aviation Administration. "Weather Delay Cost."
3. NOAA National Centers for Environmental Information. "Data Access."
