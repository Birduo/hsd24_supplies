# HSD 2024 Test Supplies

Welcome to the test supplies repo! Here, you will find various resources for testing projects. This includes:

- weather data (core data for testing)
    - `gather_data.py` gets the data from open-meteo
- mystery feature (whenever it's launched)

# Test Solutions
## A note about scoring
These examples are primarily meant to serve as guides for the type of questions we want the students to be able to answer and demonstrate during their presentations. What specifically is asked isn't as important as whether they've created a project that can accomplish these types of tasks.
- Core features: Can they query specific data points from an input file?
- Small extra feature: Can they make an API request and compare response data with an input file?
- Medium extra feature: Can they create a histogram for a given data type?
- Large extra feature: Did they create a REST API usable with HTTP requests?
- Mystery feature: Can they compare data across timeframes within a single input file? 

The following are examples of questions that the students could be asked. The cities named each correspond to a specific input file. 

## Core Features
Q: What is the minimum `temperature_min` of days 0-9 in New York City? 
> A: 43.2536 degrees Fahrenheit

Q: What is the average `wind_speed_max` of all days in Seattle? 
> A: 7.69544508 mph

Q: What was the max `precipitation_probability_max` on day 10 in Salt Lake City? 
> A: 7.0%

Q: What was the highest weather code between days 8 and 12 in Lawrence? 
> A: 3.0 (or "overcast")

## Small Extra Feature
For the next example questions, the data was obtained online with the parameters in the API link below:
> https://api.open-meteo.com/v1/forecast?latitude=38.62&longitude=-90.18&daily=temperature_2m_max&temperature_unit=fahrenheit&timezone=America%2FChicago&start_date=2024-10-02&end_date=2024-10-16

Part of the response looks like this:

```"temperature_2m_max":[74.1, 80.9, 83.7, 86.5, 81.2, 71.7, 74.7, 78.4, 81.3, 82.7, 86.2, 77.4, 61.6, 56.2, 60.5]```

Q: Compare the `temperature_max` on day 2 (2024-10-04) against the `temperature_max` on the same day at 41.87 degrees latitude -87.61 degrees longitude. 
> A: (something akin to) The given max temperature of 83.7 is greater than the max temperature of 69.7 found at 41.87 degrees latitude -87.61 degrees longitude.

Q: Compare the maximum `temperature_max` between days 4 and 9 against the same days at 41.87 degrees latitude -87.61 degrees longitude. 
> A: The given maximum `temperature_max` of 82.7 is greater than the maximum `temperature_max` of 82.5 found at 41.87 degrees latitude -87.61 degrees longitude.

## Medium Extra Feature
When drawing the histogram, please be sure to include:

- Day labels ("day 0" or "2024-10-02" for example)
- Axis labels

Q: Create a histogram of `temperature_min` between days 0 and 7. 
> A: *insert histogram here* (be sure to include axis and day labels!)

Q: Create a histogram of `wind_speed_max` between days 0 and 14. 
> A: *insert histogram here*

## Large Extra Feature
Q: Using a POST request, add the following day's data to the data for Salt Lake City in `data_1.txt` (Note: specific data may vary. What is important is that the POST request works):
```json
{
    "date": ["2024-10-18"],
    "weather_code": [1.0],
    "temperature_max": [93.1],
    "temperature_min": [84.9],
    "precipitation_sum": [0.0],
    "wind_speed_max": [15.3],
    "precipitation_probability_max": [0.0],
}
```
>A: Responses may vary, but some proof that the request was successful is required. This could be a confirmation, using a GET request to retrieve the newly posted data, etc.  

Q: Using a GET request, retrieve `wind_speed_max` and `weather_code` on **2024-10-06** in Salt Lake City, from `data_1.txt`. 

```json
{
    "date": ["2024-10-06"],
    "weather_code": [0.0],
    "wind_speed_max": [7.9939504]
}
```  

>A: Answers may vary, but as long as the data is retrieved and displayed the answer is valid. An example of a good response would be the above. 

Q: Using a PUT request, change the `wind_speed_max` on **2024-10-06** in Salt Lake City to `9.0`. Then, use a GET request to retrieve it. 

```json
{
    "date": ["2024-10-06"],
    "wind_speed_max": [9.0]
}
```  

>A: Answers may vary, but an example response is above. 

Q: Using a DELETE request, attempt to delete data for Day 5 in Salt Lake City. Then, attempt to retrieve that day's data using a GET request. 

```json
{
    "error": "Day 15 not found."
}
```

>A: This is date `2024-10-07`. When the GET is attempted, an error message should be displayed. An example is above.

## Mystery Feature (implemented during the hackathon)
_Note: See `mystery.md` for the sample data set_

Q: Compare the wind_speed_max between 2024-04-24 and 2024-04-25
> A: The wind_speed_max on 2024-04-24 was 9.31 mph, which was less than wind_speed_max on 2024-04-25.

Q: Compare the average temperature_max over days 0 through 2 against the average temperature_max over days 3 through 5.

> A: The average between days 0 through 2 was 56.51 degrees Fahrenheit, which was greater than the 51.11 degrees Fahrenheit of days 3 through 5.

Q: Compare the minimum precipitation_probability_max over the first 3 days with the minimum precipitation_probability_max over the last 3 days.

> A: The minimum precipitation_probability_max is 45% in the first 3 days, which is less than the minimum of 97% in the last 3 days.