# Event:

A company informed us that the application we deployed for them was experiencing high latency. Customers were complaining about how long it took the webpages to load. 

# Investigation:

We tested the latency of the application by sending 1000 get requests originating from the same region to the server. It took about 40 milliseconds for users to get back the content they were requesting. The server’s latency was affected rather than the processing power. 

# Resolution:

To resolve the latency, we added a CDN using AWS CloudFront. This allowed us to use Amazon’s global edge servers to deliver our static content to our customers that are not in close proximity to our servers. After using the content delivery network to store webpage html files and routing requests to hit the CDN before the web server, we tested the latency again. We were able to get the load time down to 9ms. 

In the case that the CDN isn't able to fulfill the request, it would be sent to the web server. However, adding a CDN would decrease the average latency.

While we only tested one webpage, ideally, we would want to upload all static content to the CDN to avoid requests going through the web server and backend infrastructure, taking more time.

# Purpose:

This test demonstrated how a content delivery network can significantly decrease the latency of a web application. By storing and serving content from regions and zones away from the application’s servers, we are able to improve the user experience by minimizing the time it takes for requests to be fulfilled.

# Design
![Blitz1 drawio (2)](https://github.com/nalDaniels/Blitz1/assets/135375665/92ebf055-51f3-4419-9912-d2cda7445d10)

