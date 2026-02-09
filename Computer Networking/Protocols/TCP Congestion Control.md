- When too many sources are sending too much data, too fast for the network to handle
	- CC is about network being congested. FC is about the end users and ensuring they aren't overloaded.
	- Lost packets
	- Long delays

### Parts of TCP connection
- Knee---point after which:
	- Throughput increases very Slowly
	- Delay increases rapidly
	- When throughput goes exponential -> linear
- Cliff---Point after which:
	- Throughput begins to decrease very fast to zero
	- Delay approaches infinity

### Sender window size
- Sender limits transmission: LastByteSent-LBAcked <= min (cwnd, rwnd)
- Assuming rwnd to  be very large: rate = cwnd/RTT `bytes/sec`
- Congestion window (cwnd) is a dynamic function of perceived network congestion
	- The max segments sender can transmit before receiving an ACK
	- Measured by bytes (or segments of n bytes)

# CC Algorithm
- Mechanisms of CC:
	- Slow start
	- AIMD (Congestion Avoidance)
	- Fast recovery

### Slow start
- When a TCP connection begins, cwnd begins at 1 or 2 MSS typically
	- Ex: MSS = 500 bytes, RTT = 200 msec -> Initial rate =~ 20 kbps MSS/RTT
- Rate is increased exponentially (roughly doubles cwnd every RTT)
	- One MSS (maximum segment size) increased per ack
		- Ex: two segments sent -> MSS moves from 2-> 4 when both ACKs come
- Ex:
	- Assume that ACKs are cumulative and only sent after all packets are received

| CWND | Self                               | Remoted                                                          |
| ---- | ---------------------------------- | ---------------------------------------------------------------- |
| 1    | [1, 10]                            | ACK 11 (i.e., acknowledge 1-10. ready for 11-20)                 |
| 2    | [11-20], [21-30]                   | ACK 31 (cumulative acknowledgement; 11-20 and 21-30 are grouped) |
| 4    | [31-40], [41-50]. [51-60], [61-70] | ACK 71 (acknowledged all four together)                          |

### AIMD (Congestion Avoidance)
- After slow start, linear increase of cwnd
- The transition will occur after:
	- 3 dup ACKs
		- ssTh (Slow start threshold) is halved
		- cwnd = ssTh
		- Window then grows linearly
	- Timeout
		- ssTh (Slow start threshold) is halved
		- cwnd = 1
		- Window then groes exponentially to a threshold, then linearly
	- cwnd == ssThreshold
- Additive increase: Increase cwnd by 1 MSS per RTT, instead of per ACK (until timeout)
- Multiplicative decrease: Cut cwnd in half after loss

### SS + CA
```
Assumimng ssthreshold = 4 segments
MSS = 800 B
Receiver doesn't wait 500ms
No cumulative ACK


SS ----
Cwnd increases one per ack ~= double per RTT
Per ACK, CWND += MSS Bytes
Or, CWND += 1 seg
-------

CA ----
CWND increases by 1 MSS every RTT ~= linear increase of cwnd
Per ACK, CWND += MSS/(floor[cwnd/MSS]) Bytes
Or, CWND += ~3/CWND seg
------
```

### TCP CC (Reno), summarized
- When the cwnd is below the threshold, sender is in the slow-start phase, where window growth is exponential
- When cwnd is above the threshold, sender enters congestion avoidance phase, and the window grows linearly
- When timeout occurs, threshold is halved and cwnd is set to one
