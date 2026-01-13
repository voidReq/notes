- Process: programming running
	- Can be same host, typically different in computer networking context
	- Applications with P2P have client/server processes
	- Client process: initiates communications
	- Server process: waits to be contacted
- Socket (AKA API) interfaces between application layer and transport layer
- Processes has ID (in networking, the IP and port)
	- IANA assigns 0-1023
		- HTTP: 80, HTTPS: 443, SMTP: 25, SSH: 22, DNS: 53
- Application layer ptocol defines:
	- Types of msgs (request, response)
	- Message syntax (fields)
	- Semantics (meaning of fields)
	- Rules for processing & responding
- Applications have differing requirements regarding:
	- Data reliability
	- Time
	- Throughput
	- Security

| **Application**                    | Tolerates data loss? | Throughput? | Time sensitive? | Transport protocol? |
| ---------------------------------- | -------------------- | ----------- | --------------- | ------------------- |
| File transfer, email, website, sms | No                   | Low         | No              | TCP                 |
| Real-time audio/video gaming       | Yes                  | High        | High            | UDP                 |