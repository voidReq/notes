### How do we find a destination host, given that we know its IP address on the internet?
- Interface: connection between host/router and physical link
- Subnet: Device interfaces that can physically reach eachother without passing through an intervening router
- IP addresses: 32-bit identifier with a subnet part and a host part
- Given: 223.1.1.1:
	- the last 3 bits are free for internal IPs
- Given: 223.1.1.0/24, humans can interpret this as 24 bits are dedicated to the subnet
	- The final 8 bits are for interfaces

### Example 1
- Given IP address: 223.1.1.1, subnet mask: 255.255.255.248
	- Subnet address? 223.1.1.0/29
### Example 2
- IP address: 129.17.129.97/27:
	- Network/organization address?
		- 129.17.129.96
	- Subnet?
		- 255.255.255.224
	- Total IP addresses?
		- 32
	- Assignable IP addresses?
		- 30
	- Range?
		- 129.17.129.01111111
- Say the organization wants the network divided into 4 equal size subnets. For each, write:
	- Subnet size
	- Subnet address (CIDR)
	- Subnet mask
	- Range of usable IPs
	- Broadcast address
- A
	- 129.17.129.011 00 000
		- 011 is part of the 27 bits
		- 00 is A
		- 000 is remainder of subnet address
	- 01100000 is 96 in binary
	- 129.17.129.96/29
		- 255.255.255.11111000 -> 255.255.255.248