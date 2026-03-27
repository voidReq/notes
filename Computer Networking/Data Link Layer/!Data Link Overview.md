- Layer 2
- Basic functions to move frames from one node to adjacent nodes over single communication link
### Services:
- Framing: determining where frame begins/ends
- Flow control
- Error control: detection/correction
- Reliable delivery: for links with high error rates
- Medium Access Control (MAC): rules to transmit a frame
### Implementation
- DL Layer implemented in *every* host and network device
- Mostly on a NIC (network interface card) on a chip
- Partially implemented in software, running on host's CPU
- Different links implement different link protocols
