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

The [WeatherLink v1 API](https://www.weatherlink.com/static/docs/APIdocumentation.pdf) and [WeatherLink v2 API](https://weatherlink.github.io/v2-api/) are the primary way of accessing weather observation data, but for large scale users of the WeatherLink service who need to access data from a large set of weather stations it is not ideal to be generating thousands of API calls per minute. To solve this issue the concept of the RDF was created. Instead of constantly pulling data from an API at scale a dedicated data stream can be established to receive data in real-time as it is received and processed by the WeatherLink service.

<div class="notice--warning">
<h4>Note:</h4>
<p>The RDF is intended only for large scale users of WeatherLink</p>
</div>

Each RDF data stream is an Amazon Kinesis Data Stream. The Kinesis stream is not managed by Davis Instruments, instead you will create an Amazon Web Services account and establish the Kinesis data stream in your account. This way you can control and monitor the stream. After creating the Kinesis data stream and coordinating with Davis Instruments to grant WeatherLink permission to write to the stream you will the start receiving data in real-time as it is processed by the WeatherLink service.
