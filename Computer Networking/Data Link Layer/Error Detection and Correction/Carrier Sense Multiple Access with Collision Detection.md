- Used in classical ethernet, IEEE 802.3 
- Connectionless: no handshaking between sending/receiving NICs, no connection establishment before sending frames
- Unreliable: No ACKs sent, frames in error discarded
	- ARQ (Automatic Repeat Request) vs. FEC (Forward Error Correction)
	- None of these in ethernet

### ARQ vs FEC vs Ethernet/High-Speed Ethernet
- ARQ
	- Relies heavily on error detection
		- CRC
	- Feedback: ACK/NACK
	- Retransmission 
	- Used in many layers, and in 802.11, TCP, cellular links, etc.
- FEC
	- Physical
	- Not DLL
	- Error detection/correction
	- No feedback, no retransmissions
	- Used in noisy/long distance data transmission
		- Doesn't want a retransmission if it'll take too long
	- Satellite links, fiber optics, streaming
	- Physical layer example: RS-FEC
- Ethernet
	- Only uses error detection
- High-speed Ethernet
	- Full-duplex
	- Error detection, not error correction

### Ethernet Slot Time
- Ethernet Slot Time is the max time it can take for signal to travel across entire collision domain and back
- Example in legacy half-duplex: 10 Mb/s, 512 bit times (ethernet slot time) = 64 Byte frame size = 51.2 microseconds
	- `512 bits / 8 = 64 bytes, a bit time = 1 sec / 10Mb = 0.1 ms, 512*0.1=51.2 `
- Full duplex are 10Gb/s or more, and have no collisions (so slot time is irrelevant)
- Ethernet frames are 64 bytes, so collision can be detected in classical ethernet
	- If frame is smaller, sender may finish transmitting before collision is detected

### CSMA
1) NIC receives datagram from network layer, creates a frame
2) If NIC senses idle channel, starts transmission
	- Waits otherwise
	- If detects another txm while transmitting, aborts and sends 32-bit (or 48-bit) jam signal  (alternating 1/0, ends in 11)
	- Post-aborting, enters exponential backoff:
		- m = min(n, 10), where n is the number of collision times
		- Collision detected, NIC chooses k at random: k ∈ { 0... (2^m) - 1}
		- NIC waits `k*512` bit times, returns to step 2
3) If entire frame sent without detecting another transmission, NIC done with frame
- **Exponential collision**	
	- FIRST COLLISION
		- m = min(n, 10)
		- Collision detected, NIC chooses k at random: k ∈ { 0... 2^m - 1}
		- NIC waits `k*512` bit times, returns to step 2
	- SECOND COLLISION
		- k ∈ {0, 1, 2...}
	- THIRD
		- k ∈ ()
- EX:
```
Imagine A wants to txm on classic Ethernet, using CSMA/CD
After fourth collision, what is the probability that node A chooses K=3?

k∈{0...15}, so P (k=3|n=4) = 1/16

How many microsecond delay, if K=3 on a 10Mbps Ethernet?
3*512=1536, 1536/10 = 153.6 microseconds
```

### Evolution in modern Ethernet (to avoid CSMA/CD)
- Switched Ethernet: each device connects to a switch port, not a shared bus 
	- No domain for collision to occur
- Full-duplex operation: sending and receiving simultaneously
	- CSMA/CD unnecessary
- High speeds
	- Modern ethernet only full-duplex
	- Links are point-to-point (NIC <-> switch)
	- Not a shared medium