### MAC/LAN/physical/Ethernet Address
- Used "locally" to get frame from one interface to another, physically connected interface (same network)
- 48 bit address burned into NIC ROM
- Written in hex
- Each adapter on a LAN has a unique address
- Allocation administered by IEEE
- Manufacturer buys a portion of MAC address space
- MAC flat address -> portability
- Can move between LANs
	- IP addresses aren't portable, depends on IP subnet

### ARP example
- A wants to send datagram to B
- B's MAC isn't in A's ARP table
- A broadcasts ARP query packet, w/ B's IP address
- ARP query contains sender/receiver IP/MAC, with dest MAC as FF-FF-FF-FF-FF-FF
- B receives ARP packet
	- Responds only to A w/ ARP response packet, holding B's MAC
- A caches IP/MAC address pair in ARP table until information times out
- ARP is plug-n-play, no need for net admin

# Switches 