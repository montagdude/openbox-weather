openbox-weather
================================================================================
openbox-weather: Parses NOAA weather data for openbox, tint2, or text output

openbox-weather retrieves weather and forecast data for a location from the
US National Weather Service and formats it for displaying in an Openbox pipe
menu, a tint2 executor, or plain text. Most settings, including the location,
are read from $HOME/.config/openbox-weather/config.py or the fallback
/etc/openbox-weather/config.py. Only the latitude and longitude are required,
but the script will execute faster if a weather station ID is provided (if not,
the nearest station to the given location is determined when the script runs).
To get the ID of the nearest station to the location in config.py:
```
openbox-weather -o nearest-station
```

To format output for an Openbox pipe menu to display current conditions, the
hourly forecast for the next 24 hours, and the daily forecast for the next 7
days, use
```
openbox-weather -o openbox-current
```

You will need to put something like this in your Openbox menu.xml to use it:
```
<menu id="weather-menu" label="Weather" execute="openbox-weather -o openbox-current">
</menu>
```

To format output for a tint2 executor:
```
openbox-weather -o tint2
```

And in your tint2 config script, for the executor use
```
execp_command = openbox-weather -o tint2
execp_continuous = 0
execp_has_icon = 1
execp_cache_icon = 0
```

To see other possible output options, use openbox-weather -h. Please note that
the National Weather Service does not have stations outside the US, so this
script will be of limited use in other countries.

Screenshots
================================================================================
![alt tag](https://raw.githubusercontent.com/montagdude/openbox-weather/master/screenshots/openbox1.png)
![alt tag](https://raw.githubusercontent.com/montagdude/openbox-weather/master/screenshots/openbox2.png)
![alt tag](https://raw.githubusercontent.com/montagdude/openbox-weather/master/screenshots/tint2.png)

