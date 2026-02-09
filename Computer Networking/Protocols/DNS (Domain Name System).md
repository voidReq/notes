- Created to work generally with the application layer to resolve host names

### IP
- IPv4: 4 octets/bytes, usually written in decimal
	- Not enough for each person in the world to have a unique IP address (more on NAT later)
- IPv6: 16 bytes, usually written in hex
	- ~340 undecillion addresses
- IP is part of the network layer (an IP header is added, creating a datagram)

### Routing requests
**Application Layer**
- Establishes HOSTNAME, Port, initializes socket connection
- Calls DNS, sends IP to transport layer
**Transport Layer**
- Adds header to ADU, sends to segment to Network Layer (with IP address, Port)
**Network Layer**
- Adds header to segment, containing IP address
- Sends IP datagram to DDL Layer
### DNS
- Distributed databases
	- 13 root servers (routers choose closest)
		- Thousands of actual locations
		- One IP associated with many locations per root server
	- Hierarchy extends into TLD DNS servers, which root servers query
	- Local name server
		- Each ISP has one
- Application-layer
- No user interaction
- Resolution types
	- Iterative: "tell who knows"
	- Recursive: "give the final answer" (used by end users)

### Record types
- A (AAAA for IPv6)
	- name: hostname
	- value: IP address
- NS
	- name: domain
	- value: hostname of authoritative name server for this domain
- CNAME
	- Alias name for the real name
	- value: real name
- MX
	- value: name of mailserver
- SOA
	- value: info regarding authoritative name server