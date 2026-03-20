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
### Error detection (EDC+D)
- Error correction and detection bits: EDC
- Data protected by error checking, may include header fields
- Not 100% reliability, but pretty consistent
- Larger EDC -> better detection and correction
- Detected through:
	- Parity checking
	- Checksum
	- Cyclic Redundancy Check (CRC)
		- Also called Frame Check Sequence (FCS)

- **Parity checking (1)** 
	- Single bit parity
		- Detects single-bit errors (any odd num of bits)
		- Can't detect even num of bit errors
		- No correction
	- 2d bit parity
		- Detects, corrects single bit errors
		- Detects AND corrects single-bit errors
		- Detects, doesn't correct most multi-bit

**Checksum (2)**
- Pretty straightforward

**Cyclic Redundancy Check (CRC) (3)**
- This is a little hard for me to explain in this format. 
- Until I implement an explanation, GeeksForGeeks has a great one that I'll refer you to: 
- https://www.geeksforgeeks.org/dsa/modulo-2-binary-division/
- Widely used in practice
- Binary number D, left shifted by r bits and divided by generator G
	- Goal is to choose r CRC bits, R st.
		- D||R divisible by G, modulo 2
		- Receiver knows G, divides D||R by G
		- If non-zero remainder -> error!