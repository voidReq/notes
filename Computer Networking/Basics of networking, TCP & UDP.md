- In distributed/network applications, you can have reliable vs. unreliable
	- Reliable is slower, unreliable faster (think TCP vs UDP)
- Protocols manage sending/receiving of messages
	- Human
		- Permission hierarchies
		- Access cards
		- Standardization
	- Network
		- Non-human, automated
		- Consistent
- Protocols are standardized
	- IETF: Internet Engineering Task Force (also: W3C, IEEE, ITU, etc.)
		- Start with an internet draft
		- RFC: request for comments
			- Can be used in your network
### Communication models:
- Client-Server
	- Servers provide, clients requests
	- Centralized
- P2P
	- No dedicated servers, each host can request/provide
	- Decentralized
- Overlay networks:
	- Virtual networks running atop physical infrastructure

### Data Transfer types
- Reliable: TCP (RFC 793)
	- Byte stream between the two, checks each message successful 
	- Initiates a handshake in the beginning standardizing communications
	- HTTP, FTP, SSH, etc.
- Unreliable: UDP (RFC 768)
	- Packet transfer
	- Essentially throws the message off, regardless of validity/success
	- Packets can be in wrong order, not arrive, invalid, etc.
	- Media transfer, audio/video streaming, etc.

### [[TCP]] Traffic issue remediation
- Flow control (prevention)
	- Checking for buffer space consistently (capacity)
- Congestion control (reaction)
	- Mechanism to react to current happenings


```
----------------------------------------------------
"Be conservative in what you do, be liberal in what you accept from others"
----------------------------------------------------
```

### UDP
- Best effort, connectionless (no handshake), and unreliable
- Doesn't implement flow control, congestion control
- Low overhead/small (no header, handshake, etc.)
- For time-sensitive applications

### Multi-client data transfer
- Circuit switching: send off an entire message at once, then the next
- Packet-switching: Split a message into packets, weave together messages

### Packet switching
- Data is divided into packets, which share network resources
	- Each packet uses full link bandwidth
	- Resources used as needed
- Can create waiting queues if sending rate > bandwidth
- Can create congestion, resource demand can be greater than available resources
- Good for bursty data
- Simpler
- Excessive congestion: packet delay/loss
	- Protocols needed for reliability and congestion control
- Relies upon statistical multiplexing & store and forward

### Statistical Multiplexing
- Multiple data streams share network resources
- BW shared on demand in ordered to increase utilization (avoid silent periods)

### Store and Forward
- The whole packet must arrive at router before transmitted to next link
```
Example:
R is link txm rate, link capacity, or bandwidth
L is length of packet

R = 1.5 Mb
L = 7.5 Mb

Txm delay:
one-hop pkt txm delay L/R = 7.5/1.5 = 5 sec

Essentially, it takes L/R seconds to transmit L-bit packet into link at R bps

```