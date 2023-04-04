# 19 Fetch API

## 2023-04-04

### Agenda

- Get data with fetch API in browser
- Get new data on refresh
- Show data in the interface

### Useful resources

Look here for a custom-built webserver to test your HTML. 

https://github.com/comp426-2023-spring/my-express-server

#### Fetch API docs and tutorials

[Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API) - MDN WebDocs

[JavaScript Fetch API](https://www.w3schools.com/jsref/api_fetch.asp) - w3schools

[Fetch API](https://javascript.info/fetch-api) - The Modern JavaScript Tutorial

[Fetch Standard](https://fetch.spec.whatwg.org/) - Web Hypertext Application Technology Working Group (WHATWG)

### Notes

[Open-Meteo Weather API Docs](https://open-meteo.com/en/docs)

Create your very own extremely rudimentary Chapel Hill current weather interface!

```index.html
<html>
    <head>
        <title>Chapel Hill Weather</title>
    </head>
    <body>
        <h1 id="hello">Here's the weather in Chapel Hill right now.</h1>
                <p>The current temperature in Chapel Hill is <span id="temperature">temperature</span>&#8451;.</p>
                <p>The current wind speed is <span id="windspeed">windspeed</span> kph.
    <script>
                async function getWeather() {
                        let response = await fetch('https://api.open-meteo.com/v1/forecast?latitude=35.91&longitude=-79.05&current_weather=true');
                        console.log(response.status);
                        //console.log(response.statusText);

                        let data = await response.json();
                        console.log(data);
                        let temperature = document.querySelector('#temperature');
                        console.log(temperature);
                        temperature.innerText = data.current_weather.temperature;
                        let windspeed = document.getElementById('windspeed');
                        console.log(windspeed);
                        windspeed.textContent = data.current_weather.windspeed;
                }

                getWeather();

        </script>
    </body>
</html>
```

#### Things to think about

How can we make information legible to users?

If we have JSON that looks like this, how could we turn the wind direction number into something that would make sense to a human person?

https://api.open-meteo.com/v1/forecast?latitude=35.91&longitude=-79.06&current_weather=true&temperature_unit=fahrenheit&windspeed_unit=mph&precipitation_unit=inch&timezone=America%2FNew_York

That URL should return the following(ish):

```weather.json
{"latitude":35.897686,"longitude":-79.05121,"generationtime_ms":0.17595291137695312,"utc_offset_seconds":-14400,"timezone":"America/New_York","timezone_abbreviation":"EDT","elevation":151.0,"current_weather":{"temperature":80.8,"windspeed":5.5,"winddirection":201.0,"weathercode":0,"time":"2023-04-04T18:00"}}
```

Or you can print it pretty like this, by going to https://codebeautify.org/jsonviewer: 

```weather.json
{
  "latitude": 35.897686,
  "longitude": -79.05121,
  "generationtime_ms": 0.2110004425048828,
  "utc_offset_seconds": -14400,
  "timezone": "America/New_York",
  "timezone_abbreviation": "EDT",
  "elevation": 151,
  "current_weather": {
    "temperature": 80.8,
    "windspeed": 5.5,
    "winddirection": 201,
    "weathercode": 0,
    "time": "2023-04-04T18:00"
  }
}
```
