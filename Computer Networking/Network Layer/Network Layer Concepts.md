- Forwarding
	- Move packets from a router's input link to appropriate router output link (i.e., it handles the individual steps)
	- Relies on forwarding table (result of running a routing algorithm)
- Routing:
	- Determine route taken from src to destination
- HOL blocking
	- Reduces throughput, increases latency
	- Possible solutions
		- Virtual Output Queueing
		- Advanced Scheduling Algorithms
	- Multiple layers of OSI model
		- DLL, Net layer, Transport
- Output port queueing: possible delay/loss by output buffer overflow (arrival rate exceeds output line speed)

# Scheduling Policies
- Packet scheduling: deciding which packet to send next on link
	- Ex: First come first serve, priority, round robin, weighted, etc.
- Priority schedule:
	- Arriving traffic classified by class (by header fields)
	- Packet from highest priority queue is sent (FCFS within priority class)
- Weighted Fair Queuing
	- Each class, i, has a weight (w)
	- Time is given to each queue according to associated weight
### Queuing Theory
- We try to predict performance like queuing delay, buffer size,
	- Avg num of packets in system (Little's Thm)
	- Arrival pkt process (Poisson dist)
	- Queuing (serving) discipline (FIFO, Priority Queuing, WFQ)
	- and more
