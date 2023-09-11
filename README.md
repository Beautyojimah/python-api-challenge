# python-api-challenge

## Introduction

This repository contains a folder called Weather_Vaccation. Within the Weather_Vaccation folder, there are two related projects stored in a jupyer noteboke (WeatherPyipynb and VacationPy.ipynb), and an out_data folder. WeatherPy focuses on visualizing the weather of over 500 cities of varying distances from the equator, while VacationPy aims to help plan future vacations using the data collected in WeatherPy. The output_data folder holds the saved visualizations. 

## Table of Contents

- [WeatherPy](#weatherpy)
  - [Dependencies](#dependencies)
  - [Data Collection](#data-collection)
  - [Visualization](#visualization)
  - [Linear Regression Analysis](#linear-regression-analysis)
  
- [VacationPy](#vacationpy)
  - [Dependencies](#dependencies-1)
  - [Ideal Weather Condition](#ideal-weather-condition)
  - [Hotel Mapping](#hotel-mapping)

## WeatherPy

### Dependencies

- Python
- Jupyter Notebook
- Pandas
- numpy
- requests
- time
- Matplotlib
- Scipy
- citipy
- OpenWeatherMap API

### Data Collection

Cities were randomly selected based on latitude and longitude. The OpenWeatherMap API was then used to gather data on temperature, humidity, cloudiness, and wind speed for each city. 

### Visualization

Four scatter plots were created to showcase the following relationships:

- Temperature vs. Latitude
- Humidity vs. Latitude
- Cloudiness vs. Latitude
- Wind Speed vs. Latitude

The visualized scatter plots for each relationship is saved in the out_data folder as Fig1, Fig2, Fig3 and Fig4, respectively.


### Linear Regression Analysis

The cities were separated into Northern and Southern Hemispheres. Linear regression was then computed for each relationship. The results provided insights into the correlation between the various weather attributes and latitude.

- Discussion about the linear relationship between temperature and Latitude based on Northern and Southern hemisphere:
  The relationship between temperature and latitude in the Northern hemisphere is such that an increase in the latitude results in a decrease in the temperature. Thus, showing a fairly strong inverse correlation. This is also reflected in the negative
  r-value of -0.727 obtained.

  In the Southern hemispher, however, an increase in the latitude results in an increase in the temperature. This evidences a very strong positive correlation as observed in the r-value of 0.765.

- Discussion about the linear relationship between Humidity and Latitude based on Northern and Southern hemisphere:
  The relationship between latitude and humidity in the Northern hemisphere is such that an increase in the latitude results in a slight trend indicating the likelihood of an increase in humidity. Thus, showing a moderate correlation between humidity and latitude.       This is evident in an r-value of 0.0453

  In the Southern hemisphere, the negative r-value of -0.0279 suggests very weak negative relationship between latitude and humidity. As latitude increases, there's a slight trend indicating the likelihood of a decrease in humidity.

- Discussion about the linear relationship between Cloudiness and Latitude based on Northern and Southern hemisphere: 
  
In the northern hemisphere, there is a very weak positive correlation between latitude and cloudiness. As latitude increases, there's a slight trend indicating an increase in cloudiness. However, as the r-value id close to zero, it suggest that the correlation is minimal. Hence, latitude may not be the key detrminant of cloudiness in the northern hemisphere.

In the Southern hemisphere, the correlation is very weak but slightly stronger correlation than the northen hemisphere. It implies that as latitude increases, the cloudiness increases.

The relationship between latitude and cloudiness in both hemispheres is weak. While there might be a very slight increase in cloudiness as one moves away from the equator, other geographical and meteorological factors are likely more influential in determining cloudiness.  

- Discussion about the linear relationship between Cloudiness and Latitude based on Northern and Southern hemisphere:
As latitude increases in the Northern hemisphere, there's a slight trend indicating a decrease in wind speed observed. This suggests a  weak negative relationship between wind speed and latitiude. It suggests that while latitude might have some effect on wind speed in the Northern hemisphere, it's not the predominant factor.

As latitude increases in the Southern hemisphere, there's a trend suggesting a decrease in wind speed observed. This suggests a weak negative correlation between wind speed and latitude. While this correlation is still weak, it's slightly stronger than in the Northern Hemisphere, indicating a more pronounced (yet subtle) effect of latitude on wind speed in the Southern Hemisphere.


## VacationPy

### Dependencies

- Python
- Jupyter Notebook
- Pandas
- requests
- hvplot.pandas
- geoviews
- Geoapify API

### Ideal Weather Condition

Cities were filtered from the `city_data_df` DataFrame based on ideal weather conditions:

- Max temperature between 21°C and 27°C
- Wind speed less than 4.5 m/s
- Zero cloudiness

### Hotel Mapping

A new DataFrame, `hotel_df`, was created to store city, country, coordinates, and humidity. For each city in this DataFrame, the Geoapify API was used to find the first hotel located within 10,000 meters of the city's coordinates. The results were then plotted on a map with points representing each city. The size of each point corresponded to the city's humidity, and hovering over a point displayed additional information, including the city's name and the nearest hotel.

---

## Conclusion

WeatherPy provided valuable insights into how weather conditions vary with latitude. VacationPy then utilized this data to assist in vacation planning, ensuring that users can find cities with their ideal weather conditions and nearby accommodations.
