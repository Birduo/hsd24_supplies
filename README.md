# HSD 2024 Test Supplies

Welcome to the test supplies repo! Here, you will find various resources for testing projects. This includes:

- weather data (core data for testing)
    - `gather_data.py` gets the data from open-meteo
- mystery feature (whenever it's launched)

# Test Solutions
### core features
Q: What is the minimum temperature_min of days 0-9 in New York City? A: 43.2536 degrees Fahrenheit

Q: What is the average wind_speed_max of all days in Seattle? A: 7.69544508 mph

Q: What was the max precipitation_probability_max on day 10 in Salt Lake City? A: 7.0%

Q: What was the highest weather code between days 8 and 12 in Lawrence? A: 3.0 (or "overcast")

### small extra feature
For the next example questions, the data was obtained online with the parameters in the API link below:
> https://api.open-meteo.com/v1/forecast?latitude=38.62&longitude=-90.18&daily=temperature_2m_max&temperature_unit=fahrenheit&timezone=America%2FChicago&start_date=2024-10-02&end_date=2024-10-16

Part of the response looks like this:

```"temperature_2m_max":[74.1, 80.9, 83.7, 86.5, 81.2, 71.7, 74.7, 78.4, 81.3, 82.7, 86.2, 77.4, 61.6, 56.2, 60.5]```

Q: Compare the temperature_max on day 2 (2024-10-04) against the temperature_max on the same day at 41.87 degrees latitude -87.61 degrees longitude. A: (something akin to) The given max temperature of 83.7 is greater than the max temperature of 69.7 found at 41.87 degrees latitude -87.61 degrees longitude.

Q: Compare the maximum temperature_max between days 4 and 9 against the same days at 41.87 degrees latitude -87.61 degrees longitude. A: The given maximum temperature_max of 82.7 is greater than the maximum temperature_max of 82.5 found at 41.87 degrees latitude -87.61 degrees longitude.

### medium extra feature
When drawing the histogram, please be sure to include:

day labels ("day 0" or "2024-10-02" for example)
axis labels
Q: Create a histogram of temperature_min between days 0 and 7. A: *insert histogram here* (be sure to include axis and day labels!)

Q: Create a histogram of wind_speed_max between days 0 and 14. A: *insert histogram here*

### large extra feature
