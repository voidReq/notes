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

### Example problem
10 meter link, BW: 150 bits/sec, packet size: 100,000 bits, control pkts: 200 bits.
Speed of light through link: 3E8 m/s
Initial downloaded object contains 10 objects (100k bits each)
**E2E delay?** one-way propagation delay = tp between client/server
	a) Assume parallel downloads via parallel instances on non-persistent HTTP. Assume N parallel connections each get 1/N of the link bandwidth.
	b) Now consider persistent HTTP

transaction delay: tx

- Non-persistent (new TCP connection per request)
```
We have a 10 meter link, BW: 150bits/sec
Data packet length: 100kb
Control packet length: 200b

Propagation time (tp): 10m/(3E8m/s) # we can ignore this if we'd like

The handshake: ((200b/150b/s) + tp) * 2 # 200 bits, 150 at a time. has to go there and back

Make the HTTP request (200b), 200b/150b/s
Bring back 100kb, 100kb/150b/s
In that object, there's a reference to 10 objects

Open 10 parallel objects
Since there's one link (150b/s), but 10 connections, each one becomes 15b/s
Per object:
	2([200/15] + tp)  # tcp handshake
	+ ([200/15] + tp) # the http request
	+ ([100kb/15] + tp) # receiving the actual object
	  
Non-persistent: (200/150) + (100k/150) + 10(3(200/15) + 100k(15))
```
- Persistent (without pipelining):
```
3(200/150)  # TCP handshake (there, back)
+ (100k/150)  # The initial object containing references
+ 10(200/150 + 100k/150) # each HTTP request + the object
```

- Altogether, the time is not very different
- However, persistent uses much less memory, as only one TCP connection is open

- Persistent (with pipelining)
```
3(200/150) # open TCP
+ 100k/150 # initial HTML object
###
STOP! 
Now, instead of waiting for the first object to come back, we just keep requesting, at once
Simultaneously requesting/receiving all 10 is APPROXIMATELY 2 RTTs
###
+ 2(200/150 + 100k/150) # pipelined requests
```
