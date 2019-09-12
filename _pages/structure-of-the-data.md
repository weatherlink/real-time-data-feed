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

Below is a sample JSON document from an RDF stream for an EnviroMonitor Integrated Sensor Suite (ISS) current conditions data record.

```json
{
	"data_structure_type": 6,
	"did": 8422640,
	"lsid": 5307508,
	"ts": 1568313900,
	"tz": "America/Los_Angeles",
	"tzo": -25200,
	"rain_collector": {
		"size": 0.01,
		"unit": "inches"
	},
	"data": {
		"bar": 30.091,
		"bar_absolute": 29.659,
		"bar_trend": 0,
		"dew_point": 52,
		"et_day": 0.033,
		"forecast_desc": null,
		"forecast_rule": null,
		"heat_index": 85,
		"hum_out": 30,
		"rain_15_min_clicks": 0,
		"rain_15_min_in": 0,
		"rain_15_min_mm": 0,
		"rain_60_min_clicks": 0,
		"rain_60_min_in": 0,
		"rain_60_min_mm": 0,
		"rain_24_hr_clicks": 0,
		"rain_24_hr_in": 0,
		"rain_24_hr_mm": 0,
		"rain_day_clicks": 0,
		"rain_day_in": 0,
		"rain_day_mm": 0,
		"rain_rate_clicks": 0,
		"rain_rate_in": 0,
		"rain_rate_mm": 0,
		"rain_storm_clicks": 0,
		"rain_storm_in": 0,
		"rain_storm_mm": 0,
		"rain_storm_start_date": null,
		"solar_rad": 775,
		"temp_out": 86.7,
		"thsw_index": 97,
		"uv": 4,
		"wind_chill": 87,
		"wind_dir": 95,
		"wind_dir_of_gust_10_min": 135,
		"wind_gust_10_min": 2,
		"wind_speed": 1,
		"wind_speed_2_min": 0.2,
		"wind_speed_10_min": 0.5
	}
}
```
