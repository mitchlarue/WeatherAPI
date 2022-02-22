```python
import requests
```


```python
API_KEY = "insert your API key here"
BASE_URL = "http://api.openweathermap.org/data/2.5/weather"
```


```python
city = input("What city would you like to retrieve? ")
request_url = f"{BASE_URL}?appid={API_KEY}&q={city}"

response = requests.get(request_url)

if response.status_code == 200:
    data = response.json()
    weather = data['weather'][0]['description']
    temperature = round(data['main']['temp'] - 273.15,2)
    print("You can expect these conditions: ", weather)
    print("The temperature is: ", temperature)
else:
    print("An error occured.")
```

    What city would you like to retrieve? Seattle
    You can expect these conditions:  overcast clouds
    The temperature is:  0.31



```python

```
