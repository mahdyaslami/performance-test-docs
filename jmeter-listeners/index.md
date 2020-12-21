# [JMeter Listeners - Part 3: Listeners that Calculate Distribution Metrics](https://www.blazemeter.com/blog/jmeter-listeners-part-3-listeners-calculate-distribution-metrics)

## Active Threads Over Time
 

The Active Threads Over Time listener shows how the number of active threads change over the course of the test, for each thread group in the test. The ‘chart’ tab shows the results in line chart format, and the ‘rows’ tab shows the results in bar format as well. In the ‘settings’ tab you can configure the graph plotting display. Through this graph you can monitor the simultaneous connections in your scenario and discover bottlenecks.

 
## Connect Times over Time
 

This listener shows the connect times for every sample of the script throughout the test, i.e the time it takes to establish connection over the test for each sampler. Connection time should be as low as possible, and its success rate should be defined according to your business goals.


## Bytes Throughput Over Time
 

The Bytes Throughput Over Time listener shows the number of bytes that were sent and received, per time unit, throughout the test. There are two graphs in this chart: one shows the number of bytes sent, the other shows the number of bytes received over the test. This graph gives information about the bandwidth consumption of the system and can be correlated with the response time information during the analysis.

 
## Hits per Second
 

The Hits per Second listener provides data about the number of samples executed over the period of time. Correlating the Number of Users and Hits per Second lets us simulate and measure the types and loads of usage of the website.
 
## Response Codes per Second
 

This listener shows the response codes rates from all samples per second over the test length. This graph is extremely useful in cases where the system often responds with error codes or when you need to differentiate different response codes.

## Response Latencies Over Time
 

This listener displays the latencies for every sample of the script over the test length. As the latency is the connect time plus server processing time, this graph provides the information about the time the tested server spends for the processing of the requests (samples).

 
## Response Times Distribution
 

The Response Times Distribution listener displays the response times of each sample in bar chart form. The response times are grouped by their durations. Each group is an interval, for example from 0 to t ms, from t ms to 2t ms, where t is the configured step under the settings tab of the listener. For each group the distribution of number of samples of each sampler is displayed in a bar. The graph shows the proportion between samples, according to their response time.

 
## Response Times over Time
 

This listener shows the response time variation for each sample over the period of the test.

 
## Response Time Percentiles
 

This listener shows the dependency between the percentile and the response time, and you can see the response time for any percentile. Percentile differentiation lets you split up your user group into different sizes and analyze their experience.

 
## Response Time vs Threads
 

This listener shows the change of the response time through simultaneous threads. As a rule the more active simultaneous threads are, the longer it takes the server to respond.


## Transaction Throughput vs Threads
 

This listener shows the change of throughput through simultaneous threads. This graph is similar to the response time vs threads graph, while examining the throughput instead of the response time.

 
## Transactions per Second
 

This listener shows the number of transactions per second for each sampler. This gives us insight into the load the system was dealing with.
 