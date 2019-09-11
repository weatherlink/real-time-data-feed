---
title: Accessing the RDF
permalink: /accessing-the-rdf
classes: wide
header:
  overlay_color: "#000000"
  overlay_filter: "0.0"
  overlay_image: /assets/vendor/weatherlink/images/landing.jpg
---

Data in the RDF stream is buffered and ordered, a stream reading application will need to track where it has last read data from in the stream (known as the read head) in order to fetch the next set of records correctly. While it is possible to manually access the RDF stream using the AWS SDK it will require a lot of coordination of read heads and retry logic for any network communication failures that may occur. The preferred alternative is to use what is known as the Kinesis Client Library (KCL). The KCL manages the read heads, data record deaggregation, network retries, stream reader balancing, and stream reader scaling as the Kinesis stream may grow to accommodate more data over time; thus, allowing developers to focus on data processing business logic. 

The KCL is a Java library that can be integrated with custom application code written in Java, Node.js, .NET, Python, and Ruby. Information on the KCL is available at:

- [AWS documentation on using the KCL](http://docs.aws.amazon.com/streams/latest/dev/developing-consumers-with-kcl.html)
- [KCL source code and information on GitHub](https://github.com/awslabs/amazon-kinesis-client)

When using the KCL to read data from the RDF stream an AWS account is required. The reason is that the KCL will persist read head details and worker balancing details in an Amazon DynamoDB table that the KCL creates. 

To improve data throughput and reduce network overhead data records written to the RDF stream will be aggregated together when possible. The KCL will automatically deaggregate the aggregated records as it reads them from the stream and deliver the collection of deaggregated records to the custom business logic for processing.
