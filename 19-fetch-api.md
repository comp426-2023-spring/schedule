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
