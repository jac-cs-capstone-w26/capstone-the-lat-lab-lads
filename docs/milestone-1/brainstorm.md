# Project Brainstorming

## Purpose

The purpose of this project is to help hikers keep safe whenever they are venturing up mountains or other high elevations, as well as offer optimal hiking locations should the user ask for them. They will not have to worry about overheating, freezing, getting lost or losing oxygen via altitude sickness wherever they go, as our system is intended to alert a user of any approaching dangers in all of these categories at any time, meaning risk is brought down to a minimum.

## Subsystems

### Subsystem 1 - GPS

Our first subsystem will primarily revolve around location tracking and suggesting. Apart from logging the user's actual location and the properties of their immediate environment (which plays into the second subsystem), this subsystem will also suggest other hiking spots near by that are of similar caliber to their current location (e.g. maximum altitude, temperature, distance, etc.)

#### Devices

| Device | Interface Type | Documentation |
| :----- | :-----: | :-----: |
| GPS (Air530) | Serial | [Pyserial Library to read serial data](https://github.com/Seeed-Studio/grove.py/blob/master/grove/grove_temperature_humidity_aht20.py](https://pythonhosted.org/pyserial/shortintro.html)), [Pynmea2 to parse GPS messages](https://github.com/Knio/pynmea2), [Grove Wiki](https://wiki.seeedstudio.com/Grove-GPS-Air530/) |
| USB Power Bank | N/A | N/A |

### Subsystem 2 - Warning System

Our second subsystem will utilize the live data gathered from the GPS subsystem and use it to determine whether the surrounding environment is safe for the user or not. Things like dangerous temperatures of either extreme, incoming weather phenomena (storms, blizzards, etc.), poor air quality, or thinner atmosphere as a result of high altitudes will result in the subsystem sounding and alert to the user that they are either approaching or are actively in a dangerous environment and should seek shelter or escape.

#### Devices

| Device | Interface Type | Documentation |
| :----- | :-----: | :-----: |
| AHT20 Temp & Humidity Sensor | I2C | [Link to Python Script](https://github.com/Seeed-Studio/grove.py/blob/master/grove/grove_temperature_humidity_aht20.py) |
| reTerminal’s built-in buzzer | I2C (I/O expander) | [Example of Buzzer Use](https://github.com/Seeed-Studio/Seeed_Python_RPi) |
| Cooling Fan | Digital | [Fan Module Setup](https://docs.google.com/document/d/1M3LKarz0A299S5vM3ysqtHiEnGWiEEBzVWy4iCj3lYc/edit?tab=t.0#heading=h.uk0mchuxyo2w) |
