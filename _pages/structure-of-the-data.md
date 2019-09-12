---
title: Structure of the Data
permalink: /structure-of-the-data
classes: wide
header:
  overlay_color: "#000000"
  overlay_filter: "0.0"
  overlay_image: /assets/vendor/weatherlink/images/landing.jpg
---

Data records in an RDF stream are formatted in JSON.

## Sample Data Record

Below is a sample JSON document from an RDF stream for a WeatherLink Live Integrated Sensor Suite (ISS) current conditions data record.

```json
{
	"sensor_type": 45,
	"data_structure_type": 10,
	"did": 7405620,
	"lsid": 5271273,
	"ts": 1568318826,
	"tz": "America/Los_Angeles",
	"tzo": -25200,
	"rain_collector": {
		"size": 0.01,
		"unit": "inches"
	},
	"data": {
		"temp": 93.4,
		"hum": 19,
		"dew_point": 45,
		"wet_bulb": 53.7,
		"heat_index": 90.3,
		"wind_chill": 93.4,
		"thw_index": 90.3,
		"thsw_index": 100.5,
		"wind_speed_last": 1,
		"wind_dir_last": 257,
		"wind_speed_avg_last_1_min": 0.56,
		"wind_dir_scalar_avg_last_1_min": 296,
		"wind_speed_avg_last_2_min": 0.81,
		"wind_dir_scalar_avg_last_2_min": 38,
		"wind_speed_hi_last_2_min": 2,
		"wind_dir_at_hi_speed_last_2_min": 37,
		"wind_speed_avg_last_10_min": 0.62,
		"wind_dir_scalar_avg_last_10_min": 99,
		"wind_speed_hi_last_10_min": 3,
		"wind_dir_at_hi_speed_last_10_min": 43,
		"rain_rate_last_clicks": 0,
		"rain_rate_last_in": 0,
		"rain_rate_last_mm": 0,
		"rain_rate_hi_clicks": 0,
		"rain_rate_hi_in": 0,
		"rain_rate_hi_mm": 0,
		"rainfall_last_15_min_clicks": 0,
		"rainfall_last_15_min_in": 0,
		"rainfall_last_15_min_mm": 0,
		"rain_rate_hi_last_15_min_clicks": 0,
		"rain_rate_hi_last_15_min_in": 0,
		"rain_rate_hi_last_15_min_mm": 0,
		"rainfall_last_60_min_clicks": 0,
		"rainfall_last_60_min_in": 0,
		"rainfall_last_60_min_mm": 0,
		"rainfall_last_24_hr_clicks": 0,
		"rainfall_last_24_hr_in": 0,
		"rainfall_last_24_hr_mm": 0,
		"rain_storm_clicks": 0,
		"rain_storm_in": 0,
		"rain_storm_mm": 0,
		"rain_storm_start_at": null,
		"solar_rad": 821,
		"uv_index": 5.5,
		"rx_state": 0,
		"trans_battery_flag": 0,
		"rainfall_daily_clicks": 0,
		"rainfall_daily_in": 0,
		"rainfall_daily_mm": 0,
		"rainfall_monthly_clicks": 0,
		"rainfall_monthly_in": 0,
		"rainfall_monthly_mm": 0,
		"rainfall_year_clicks": 120,
		"rainfall_year_in": 1.2,
		"rainfall_year_mm": 30.48,
		"rain_storm_last_clicks": 3,
		"rain_storm_last_in": 0.03,
		"rain_storm_last_mm": 0.762,
		"rain_storm_last_start_at": 1559879160,
		"rain_storm_last_end_at": 1559970061
	}
}
```

And here is a sample JSON document for a Davis Instruments 6440 Soil Moisture Sensor that is part of an EnviroMonitor installation.

```json
{
	"sensor_type": 108,
	"data_structure_type": 9,
	"lsid": 5307497,
	"ts": 1568318700,
	"tz": "America/Los_Angeles",
	"tzo": -25200,
	"data": {
		"moist_soil_last": 22.2
	}
}
```

## Data Record Structure

RDF JSON data records follow a fairly consistent format regardless of the type of weather station or data record type.

A data record is composed of the following components:

- `sensor_type` - The sensor type can be used to cross reference with the [Sensor Catalog](https://weatherlink.github.io/v2-api/sensor-catalog) from the WeatherLink v2 API to find documentation on the field names and data types for all data fields supported by each type of sensor.
- `data_structure_type` - The data structure type is used to further specify the nature of a data record when the sensor supports generating multiple types of data records. Please see the [Data Structure Types](https://weatherlink.github.io/v2-api/data-structure-types) page from the WeatherLink v2 API for more details.
- `lsid` - The Logical Sensor ID. This is a unique ID for the sensor.
- `did` - The Device ID. This is the decimal representation of the hexadecimal Device ID identification number on WeatherLink connected devices. This field is only present for ISS sensors.
- `ts` - The Unix timestamp of the data record.
- `tz` - The IANA time zone name for the weather station's selected time zone.
- `tzo` - The time zone offset from UTC.
- `rain_collector` - If the sensor is an ISS or rain collector sensor there will be information about the measurement size and unit type of the rain collector. If the sensor is not an ISS or rain collector this field will not be included.
- `data` - The data field contains all of the data fields reported by the sensor.

