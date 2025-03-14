# Data_Science_Project
# An Analysis of Flight Delay with Weather Conditions

## Project Overview
This project aims to analyze how weather conditions impact flight delays and cancellations across US airports. By combining comprehensive flight data with detailed weather observations, the project will develop predictive models to forecast potential delays based on weather patterns and other operational factors. The analysis will identify which weather conditions are most disruptive to air travel and how these impacts vary across different airports, airlines, and seasons.

## Motivation
It is a common occurance that flights get cancelled or delayed I chose this project because of its significant real-world applications in the aviation industry. Flight delays cost airlines and passengers billions of dollars annually, and weather is responsible for approximately 70% of all delays. By understanding the relationship between specific weather conditions and flight performance:

1. Airlines could better anticipate and mitigate delays
2. Airports could optimize resource allocation during adverse weather
3. Passengers could make more informed travel decisions
4. The industry could potentially reduce the economic impact of weather-related disruptions

As an engineering student interested in transportation systems and data science, this project allows me to apply machine learning techniques to solve a complex problem with multiple variables and stakeholders.

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
4. Create a delay risk scoring system for different weather scenarios1

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


