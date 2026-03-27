- Wireless links, in contrast to wired
	- Wireless are far more crowded
	- Work for battery constraint
	- Mobile support
- SNR: Signal-to-Noise ratio
	- SNR = `10*log(|S|/|N|)`
	- Larger SNR -> easier to extract signal from noise (good)
- Wireless BER (bit error rates)
	- Higher than in wired networks
	- Errors often occur in bursts
	- Variers over time of connection
- Hidden terminal problem
	- Imagine you have 3 devices: A, B, and C. 
	- A & B can hear each other, B & C can hear each other
	- A & C cannot hear eachother, meaning A & C are unaware of their interference at B
- Riddle me this: As a mobile node gets farther and farther away from a base station, how can we ensure that loss probability doesn't spike?
	1) Increase transmission power
		- Lots more battery consumption and increased radiation
	2) Reducing transmission rate
		- Introducing FEC (decreases good throughput, other physical layer reasons)

# Wireless MAC
### CDMA (Physical Layer Protocol)
- Uses spread spectrum technology, to signal spread over frequencies
	- Highly resistant to interference
	- Supports large number of users
	- FHSS (Frequency hoping spread spectrum)
	- DSSS (Direct Sequence Spread Spectrum)
	- CDMA (Code Division Multiple Access)
### 802.111 CSMA/CA
 - CA: Backoff + ACK mechanism
 - No CD, because wireless nodes can't transmit and listen at the same time
 - Missing ACK is the only indicator of interference
 - 802.111 uses Stop-and-wait
 - Modern 802.111 bundles multiple frames
	 - Block ACK, bitmap-based, not cumulative, each bit on bitmap indicates success/failure of a specific frame
	 - Sender only retransmits missing frames, and then a BlockAck Request
	 - Receiver sends one Block ACK containing the bitmap