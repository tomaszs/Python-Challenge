# Fetch Weather Data Without an API Key

## The Challenge

Write a Python script that retrieves the current weather data for a specified city using a public weather API that does not require an API key and displays the temperature, weather conditions, and other details.

### Example Interaction:

```
Enter a city name: London
The current temperature in London is 15°C with clear skies.
```

---

## Tips:

1. **Use wttr.in API:** This API provides weather data without requiring an API key.  
2. **Send an HTTP GET Request:** Use Python’s `requests` library to fetch data.  
3. **Parse the Response:** The API returns data in plain text or JSON format. For this challenge, we’ll use the plain text output.

---

## Solution:

### Install Required Libraries

If you don’t already have the necessary library installed, use the following command:

```bash
pip install requests
```

### Complete Code

```python
import requests

def get_weather(city_name):
    try:
        # wttr.in API endpoint
        url = f"http://wttr.in/{city_name}?format=%C+%t"
        
        # Send a request to the API
        response = requests.get(url)
        response.raise_for_status()  # Check for HTTP request errors
        
        # Parse and display the response
        weather_info = response.text.strip()
        print(f"The weather in {city_name} is: {weather_info}")
    except requests.exceptions.RequestException as e:
        print(f"An error occurred: {e}")
    except Exception as e:
        print(f"Something went wrong: {e}")

# Example usage
city = input("Enter a city name: ")
get_weather(city)
```

---

## Walkthrough: How the Script Works

1. **Choose a Public API:**  
   - The `wttr.in` API provides weather information directly through a simple URL.  
   - The endpoint is `http://wttr.in/<city_name>?format=%C+%t`, where:  
     - `%C` gives the weather condition (e.g., "clear skies").  
     - `%t` gives the temperature (e.g., "+15°C").

2. **Send a Request:**  
   - Use `requests.get()` to fetch the weather data.  
   - The `raise_for_status()` method ensures the request was successful.

3. **Process the Response:**  
   - The response is a plain text string. Use `.text.strip()` to clean up any whitespace.  
   - Display the result in a readable format.

4. **Handle Errors:**  
   - Use `try-except` blocks to catch connection issues or invalid city names.  

---

## Why This Challenge Matters

This task introduces you to:  
- **APIs Without Keys:** Learn to interact with simple public APIs.  
- **String Formatting:** Handle plain text responses effectively.  
- **Error Handling:** Write robust scripts that handle user input and HTTP issues gracefully.

---

## Challenge Yourself Further

1. Extend the script to display additional data, such as wind speed or humidity, using `wttr.in` options.  
2. Add support for searching multiple cities at once.  
3. Save the weather data to a log file for later analysis.  
4. Display the weather in a graphical format using Python’s `matplotlib` or `Tkinter`.

---

Solving this challenge earns you **3 points**—fantastic work! Ready to take your weather scripting skills further? Try adding more features or exploring other public APIs!
