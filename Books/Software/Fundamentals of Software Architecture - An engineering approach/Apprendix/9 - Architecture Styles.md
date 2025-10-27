1. List the eight fallacies of distributed computing.
- the network is reliable
- latency is zero
- bandwidth is infinite
- the network is secure
- the topology never changes
- there is only one administrator
- transport cost is zero
- the network is homogeneous

2. Name three challenges that distributed architectures have that monolithic archi‐
tectures don’t.
- managing network calls
- observability
- managing shared state within different services

3. What is stamp coupling?
- When you share more data than necessary, you utilize the network to send 10kb but only uses a single attribute that represents a few bytes

4. What are some ways of addressing stamp coupling?
- creating modular dtos
- graphql