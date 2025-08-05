A bit about [[Web Server]] Architecture

## Single Tier

One single Web Server for both processing and delivering webcontent. Optimal for low traffic environments.

1. User requests for server IP in DNS server
	
2. User requests to web server IP
	
3. Web server responds

## Multiple Tier

Multiple server are used to distribute load. Load balancers evenly distribute requests across a cluster of web server, which can server web content independently.

1. User requests for server IP in DNS server
	
2. User requests to Load balancer
	
3. Load balancer redirects request to a healthy web server
	
4. Web server responds