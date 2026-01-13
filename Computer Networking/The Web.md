- Utilizes HTTP/HTTPS
- Web 1 (r), Web 2 (rw, centralized), and Web 3 (decentralization, blockchains, smart contracts, AI/ML)

| HTTP Version | Features                                                                                          |
| ------------ | ------------------------------------------------------------------------------------------------- |
| HTTP/1.0     | Headers, status codes, POST, caching, new TCP connection per request                              |
| HTTP/1.1     | Persistent connections, pipelining, chunked transfer encoding, advanced caching                   |
| HTTP/2.0     | Multiplexing, header compression, server push, improved performance                               |
| HTTP/3.0     | Starts using QUIC instead of TCP. Reduced latency, no head-of-line blocking, optimized for mobile |
- HTTP/<2.0 uses TCP
- Nonpersistent HTTP (HTTP/1.0 and earlier)
	- First makes TCP connection (one RTT: round-trip time)
	- Then sends HTTP request, gets HTML (one RTT)
	- Total time: 2RTT + transmit time
	- One object sent over TCP connection at most
	
- Persistent HTTP with pipelining (HTTP/1.1)
	- Multiple objects sent over a single TCP connection
	- First makes TCP connection (one RTT)
	- Sends HTTP request, gets HTML
		- Leaves open connection, makes requests for every reference in the page
		- Roughly one RTT
	- Total time: 2RTT

- HTTP request messsages:
- 