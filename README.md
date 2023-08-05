# Weather-Fetcher1
This program utilizes an API to fetch and display the weather information of any city in the world, allowing users to stay updated on weather conditions worldwide.

#### Installing request libraries and importing requests
```
pip install requests
import requests
```
Using pip install requests allows you to quickly install the "requests" library in Python, simplifying HTTP requests and enabling easy interaction with web APIs to retrieve data from websites and web services. Once installed, you can use the "requests" library in your Python code to perform various HTTP operations and handle responses from web servers.

#### Collecting an API
Visit the site: 
https://openweathermap.org/api

```
BASE_URL = 'http://api.openweathermap.org/data/2.5/weather'
```
To collect a unique API code. The weather website will provide a code that will allow to connect to a weather API. 

```
city = input('Enter a City Name: ') # The user will enter a city of their choice when prompted. 
request_url = f'{BASE_URL}?appid={API_KEY}&q={city}' # A request URL is created where the url will integrate the API key, city and the URL. 
```
In this code, the user is prompted to input a city name, which is stored in the variable city using the input() function. The request_url variable is then constructed using an f-string, incorporating the BASE_URL, API_KEY, and the user-provided city to create a URL for making an API request to fetch weather data for the specified city.

```
response = requests.get(request_url)  # sends an HTTP GET request to the URL specified in request_url,

if response.status_code == 200:
    data = response.json() # The result is written in jSon, and the variable data stores the information
    weather = data['weather'][0]['description'] # weather is recorded in the first index of the weather
    print(weather)
    temperature = data['main']['temp'] - 273.15 # returning in Celcius 
    print(temperature)

else:
    print('An Error Occured.')
```

In this code, requests.get(request_url) sends an HTTP GET request to the URL specified in request_url. If the response status code is 200 (indicating a successful request), the JSON data from the response is extracted using response.json(), and the weather description and temperature for the specified city are printed. If the response status code is not 200, an error message, "An Error Occurred," is printed.

For example, 
If you enter, Toronto, for the prompt, the code will connect to the weather data base through an API which will return the weather and temperature. 





