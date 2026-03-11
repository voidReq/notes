# IPv4
- IPv4 Datagrams:
	- Version number, header ln, service type, datagram ln
	- Fragmentation offset, flags, 16-bit identifier
		- ID flag: 1 if there are more fragments after, 0 if there aren't
		- Offset: How many units have already been sent (byte size of all previous, not including header, divided by 8)
	- TTL, upper layer (send to TCP or UDP?), header checksum
	- Source IP
	- Destination IP
	- Options
	- Payload
- Fragmentation & Reassembly
	- Links have MTUs---therefore, datagrams must be fragmented if IP hdr + Transport Hdr + MSS are greater than MTU
	- Given a 4000 Byte datagram, and an MTU of 1500 Bytes:
		- 4000-20=3980 (Remove IP Hdr)
		- 1500-20=1480 (For IP Hdr)
		- 3980/1480 = 2.68 (therefore, 3 fragments)
	- Fragmentation is discouraged
	