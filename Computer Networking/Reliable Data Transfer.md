...
I missed a fair amount of content
...
# Pipelining
- Go back in
	- Local waits for an eventual response from server containing an adjusted window size, and adjusts to it
	- If local receives a timeout, local attempts resending the packets
		- Timer is based upon oldest packet sent
	- If server receives an out of sequence packet, it won't be buffered
		- This is because the server knows local will send all of the packets again
	- Ideal for channels with large, chunked packet losses
- Selective repeat
	- Data is still sent off, and a response is waited for for a packet
	- When there's a timeout on a packet response, only that one packet is resent
	- Ideal for channels with small, individual losses
	- Window size must be less than or equal to half the size of seq# space
	