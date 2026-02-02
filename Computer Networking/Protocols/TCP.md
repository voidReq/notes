### Characteristics
- Point-to-Point
	- One sender, one receiver
- Ordered byte stream
- Pipelined
	- Congestion and flow control
		- Sender and receiver buffers
	- Set window size
- Connection-oriented
	- TCP handshake (syn, syn-ack, ack)
	- Consistent handshaking/communication
- Full duplex data
	- Bi-directional data flow in same connection
- MSS (Maximum segment size)
	- Max size of application layer data
	- Determined by link size (maximum transfer unit)
### TCP SEGMENT
- 20 byte header
- Source port #, dest port # 
- Sequence number & acknowledgement number (counting by bytes, not segments)
- RST, SYN, FIN commands
- Receive window (# bytes receiver willing to accept)
- Options & data (variable length)

# Phases
### Handshake
- Client sends TCP SYN segment
	- Specifies initial seq # 
	- No data
- Server receives SYN, replies with SYNACK segment
	- Server allocates buffers
	- Specifies server initial seq #
- Client receives SYNACK, replies with ACK
	- May contain data
	- Client allocates
### Seq, ACKs (data transfer)
- Seq # is first byte in a segment's data
	- (nowadays) Randomized and unpredictable to prevent attackers from injecting malicious packets
- ACKs: seq# of next byte expected
- ACK packets don't consume seq#
- SYN, FIN do consume seq# despite having no bytes on payload
- Data segments consume segment #'s
### Closing a connection
- 0x011 (FIN, ACK) is sent by local
	- Server responds with 0x011 (FIN, ACK)

# Timeouts
- Data received from the app creates a segment + seq # 
	- Timer is started
- Timeout:
	- rtxm segment that caused timeout
	- Timer restarted
- ACK received
```
lost ACK ex:
A sends data
B receieves, sends it back, but the packet is lost
A times out, resends data

premature timeout ex:
A sends Seq 92 and seq 100
B sends back ACK 100 and ACK 120
However, takes too long and A resends Seq 92
B throws away duplicate, resends ACK 120

cumulative ACK ex:
A sends Seq 92
B sends ACK 100, but it gets lost
A sends Seq 100 at same time
B sends ACK 120
```


| **RECEIVER EVENT**                                                               | **TCP ACTION**                                 |
| -------------------------------------------------------------------------------- | ---------------------------------------------- |
| Arrival of in-order segment w/ expected seq #, previous data already ACKed       | Delayed ACK 500ms                              |
| Arrival of in-order segment w/ expected seq #. One other segment has ACK pending | Immediately send cumulative ACK                |
| Arrival of out-of-order segment higher-than-expected seq #. Gap detected         | Immediately send duplicate ACK (expected byte) |
