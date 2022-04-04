# World Weather Analysis
## Project Overview
The new PlanMyTrip app is gaining a lot of interest and love from Jack and beta testers alike and they recommended the following changes to take the app to the next level:

1. Add the weather description to the weather data you’ve already retrieved from the OpenWeatherMap API 
2. Filter the data for their weather preferences using user input statements, which will identify potential travel destinations and nearby hotels 
3. From the list of potential travel destinations, choose four cities to create a travel itinerary and using the Google Directions API, create a travel route between the four cities as well as a marker layer map

## Summary
The following deliverables have been created:

1. [Retrieve Weather Data](/Weather_Database/Weather_Database.ipynb)
    - From a set of 2,000 random latitudes and longitudes, the nearest city was retrieved for 765 records using the citipy module.
    - In addition to the city weather data that was previously gathered (i.e. latitude, longitude, max temperature, percent humidity, percent cloudiness, and wind speed), we also retrieved the current weather description (for example, clouds, fog, light rain, clear sky) for each availale city using the OpenWeatherMap API.
    - The new [WeatherPy_Database](/Weather_Database/WeatherPy_Database.csv) DataFrame was created and exported as a CSV file - it has a total of 708 records. 

2. Create a [Customer Travel Destinations Map](/Vacation_Search/Vacation_Search.ipynb)
    - Using input statements, we retrieved the user's weather preferences (i.e., minimum and maximum temperature critiera for their vacation). For example, there were 278 destinations in our WeatherPY database that had max temperature between 70 and 90 degrees F.
    - A total of 263 [nearby hotels](/Vacation_Search/WeatherPy_vacation.csv) were identified using those preferences and saved as a CSV file.
    - Using the gmaps module, we were able to show the hotels on a [marker layer map](/Vacation_Search/WeatherPy_vacation_map.png) with pop-up markers when selected. When you select a marker, the hotel name, the city name, the country code, the weather description, and the max temperature for the city will be provided.
    
3. Create a [Travel Itinerary Map](/Vacation_Itinerary/Vacation_Itinerary.ipynb)
    - Using the Goggle Directions API, a [travel itinerary map](/Vacation_Itinerary/WeatherPy_travel_map.png) that show the route between 4 cities chosen froom the customer's possible travel destinations was created. For example, four cities - Sira, Srivardhan, Baihar, and Puri -- in India were chosen that a customer might want to visit.
    - By combining the 4 separate city DataFrames into one DataFrame, we created a new [marker layer map](/Vacation_Itinerary/WeatherPy_travel_map_markers.png) of the cities on the travel route.

## Resources
- Data Sources: WeatherPy_Database.csv
- APIs: OpenWeatherMap, Google Nearby Places, Google Maps Directions
- Software: Python 3.7.6, Jupyter Notebook 6.4.5