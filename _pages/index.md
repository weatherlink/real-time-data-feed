---
title: Introduction
permalink: /
classes: wide
header:
  overlay_color: "#000000"
  overlay_filter: "0.0"
  overlay_image: /assets/vendor/weatherlink/images/landing.jpg
---

The WeatherLink Real-time Data Feed, referred to as RDF from here on, is a real-time data stream of the weather observation data records for WeatherLink connected weather stations that you have access to.

The [WeatherLink v1 API](https://www.weatherlink.com/static/docs/APIdocumentation.pdf) and [WeatherLink v2 API](https://weatherlink.github.io/v2-api/) are the primary way of accessing weather observation data, but for large scale users of the WeatherLink service who have access to a large set of weather stations it is not ideal to be generating thousands of API calls per minute. Instead, the RDF was created to copy data as it is processed by the WeatherLink service into dedicated data streams for large scale users of the WeatherLink service.
