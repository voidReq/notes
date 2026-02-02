- Using models helps us organize and dedicate parts of networks
- Typically OSI or TCP
### TCP/IP
- 5 layers, made by US DoD
	- Application: service to users
		- FTP, SMTP, HTTP, HTTPS, SSH, etc.
	- Transport: Process-process data transfer
		- TCP, UDP, etc.
	- Network: routing
		- IP, routing protocols
	- Data link: data transfer between neighboring network elements
		- PPP, Ethernet
	- Physical: bits "on the wire"
	- Application, transport, network, link, physical
	- Each layer communicates only w/ layers that it borders
- Encapsulation: wrapping data as it moves down the protocol stack

```
LAYER 5 (application): imagine a message, 10kb. Split it into application data units (ADUs)
LAYER 4 (transport): ADU moves into transport layer. A header is added. You now have a segment. Our header (i.e., that of the sender) communicates with the transport layer of the receiver. 
LAYER 3 (network): A header of the network layer is added. We now have a datagram
Layer 2 (data link): Creates a frame from the datagram, often adds metadata. Our "message" is now handed off to the next device (e.g., router)

Now, on the other device
```
- PDU: Protocol data unit (ADU, segment, datagram, datagram, frame)


### QUIC (Quick UDP Internet Connections)
- Breaks traditional layering by running on top of UDP
- HTTP/3 -> QUIC -> UDP
- QUICK & UDP effectively function as transport layer

### Layering

| Pros             | Cons                                                                                                           |
| ---------------- | -------------------------------------------------------------------------------------------------------------- |
| Modularity       | Limited                                                                                                        |
| Innovation       | Redundancies                                                                                                   |
| Interoperability | Violated everywhere: Firewalls (inspect data at many layers, which is typically only at application), NAT, DPI |
| Simplicity       |                                                                                                                |

- E2E Principle (highly controversial & influential, made by MIT researchers in '80s):
	- Don't implement function at lower levels of system UNLESS does one of the following:
		- Can be completely implemented at this level
		- Improves performance
	- Unless you can completely remove burden from end hosts, don't bother
	- Keep network simple & dump
		- Put intelligence on edges (endpoints)