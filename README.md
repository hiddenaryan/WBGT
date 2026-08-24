# WBGT Calculation from Weather & Radiation Data

This project calculates the **Wet Bulb Globe Temperature (WBGT)** using weather forecast data and solar/radiation data.

## Overview

WBGT is a heat-stress index used to estimate the effect of **temperature, humidity, wind, and solar radiation** on the human body.

This implementation uses the **Liljegren et al. method** to estimate WBGT from meteorological and radiation data.

## Inputs

The program requires two JSON files:

* `5day_3hr_new_openweather.json` — Weather forecast data from OpenWeather
* `Hourly_radiation_new_openweather.json` — Hourly radiation/solar data

The weather data provides parameters such as:

* Air temperature
* Relative humidity
* Wind speed
* Atmospheric conditions

The radiation data provides information required for estimating the **globe temperature** and solar heat load.

## Output

The program processes each forecast record and calculates:

* Natural Wet Bulb Temperature
* Globe Temperature
* WBGT
* Heat-stress conditions

The calculated results can be used for **heat-stress monitoring and forecasting**.

## How to Run

Make sure Python is installed and the required JSON files are in the same directory as the Python script.

Run:

```bash
python "WBGT_Liljegren_JSON.py" --weather "5day_3hr_new_openweather.json" --radiation "Hourly_radiation_new_openweather.json"
```

Example output:

```text
Processed 40 forecast records.
```

## Methodology

The calculation follows the **Liljegren WBGT model**, which estimates WBGT using meteorological conditions and radiation.

For outdoor conditions:

```text
WBGT = 0.7 × Tnwb + 0.2 × Tg + 0.1 × Ta
```

where:

* `Tnwb` = Natural wet-bulb temperature
* `Tg` = Globe temperature
* `Ta` = Air temperature

The model accounts for environmental factors such as humidity, wind speed, air temperature, and radiation.

## Project Structure

```text
WBGT Project/
│
├── WBGT_Liljegren_JSON.py
├── 5day_3hr_new_openweather.json
├── Hourly_radiation_new_openweather.json
└── README.md
```

## Applications

This system can be used for:

* Heat-stress monitoring
* Outdoor worker safety
* Sports and physical activity monitoring
* Heat-wave early warning systems
* Weather-based health-risk assessment

## Technologies Used

* Python
* JSON
* OpenWeather API data
* Liljegren WBGT model

## Note

The accuracy of WBGT depends on the quality and resolution of the input weather and radiation data. The implementation is intended for **environmental heat-stress estimation**, not medical diagnosis.


Developed as part of a **Smart India Hackathon (SIH)** project.


