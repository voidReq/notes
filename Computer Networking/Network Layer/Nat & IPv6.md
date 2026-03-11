- As `2^32` addresses ien't enough, network address translation (NAT) and IPv6 were made
### NAT
- All devices in one local network share one IPv4, as far as the outside world is concerned
- All datagrams leaving local network have same source NAT IP, but different source ports
- Datagrams w/ source/destination in an example home network have 10.0.0/24 address for src/destination
### IPv6
- Instead of 32-bit addresses, IPv6 has 128-bit addresses 4 sets of 32 bits
- Typically expressed with hexadecimal addresses
- No checksum
- Difficult to change the entire internet

### IPv4 -> IPv6
- Not all routers can be simultaneously updated
	- IPv4 and IPv6 routers are mixed
- Tunneling: IPv6 datagram carried as payload in IPv4 datagram, among IPv4 routers ("packet within a packet")
- 