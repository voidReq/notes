### Little's formula
- L = λD
- Relates:
	- Avg num of items in a queuing system (L)
		- Includes packets in buffer and packets being txmed
	- Avg delay in system for an item (D)
		- D = average service time (including txm time) + average waiting time
		- Arrival rate (pps)
			- Packets per unit time arriving to the router
		- Service rate (pps)
			- Processing time: header inspection, forwarding table lookup
	- Avg num of items arriving per unit time (λ)
```
Ex:
Suppose that on average, buffer has 10 packets and avg queuing delay is 10msec. Link's transmission rate is 100 packets/sec. What is avg packet arrival rate? 1 packet in txm.

Q delay: 10 msec
Transmission rate = 100 pps


Avg packet arrival rate = λ = L/D
D = Q delay + Txm delay = 10msec + 1pkt*(1 sec / 100 pkts)
									- 0.01 sec + 0.01 sec = 0.02 sec
L = 11 (10 in buffer, 1 in txm)
λ = 11/0.02 = 550
```

- A/S/m
	- Arrival process/Service Process/#servers
	- A: usually Poisson -> probability of how many packets avg per unit time
	- S: exponential, deterministic, general
- MGD (M/M/1, M/M/m, M/D/1, M/G/1, etc.)
	- M: Memoryless (Poisson arrivals, exponential service) 
	- G: General (any distribution)
	- D: deterministic, fixed service time

### M/M/1
- Poisson arrivals, exponential service time, 1 processor
- Arrival rate λ
- Service number u
- Avg # of items in a queuing system L = λ/(u-λ)
- Ex: A router processes packets at a rate of 100 pkts/sec. Packets arrive at a rate of 80 pkts/sec (λ)
	- Utilization of the processor?
		- This is λ/u
		- 80/100 = 0.8
	- Avg # of packets in the system?
		- This is L. We know that L = 80/(u-80)
		- u is the service rate = 100
		- 80/(100-80) = 4
	- Traffic intensity?
		- This is also λ/u = 0.8


### Poisson Distributions
- For a router, the arrival rate can be poissoned and process rates are typically exponential
- Poisson -> memoryless (discrete), IID
- Answers the # of events (in our case, # of packets) in time or space
	- Ex: you listen to 5 songs per day, on average (λ)
	- What is the probability that today, you listen to 2 songs? -> Poisson
- The average = λ
- P(X=x) = Poisson (e.g., P(X=2)?)
- P(X=x) = `(λ^x)*(e^-λ)/(x!)`
	- P(X=2) = `(5^2)*(e^-5)/2!`
### Exponential Distributions
- Continuous
- P(Service time >= t) = `e^-ut`
	- Recall that u is the service number
- P(Service time < t) = `1-e^-ut`
- To find probability, you integrate the curve 


### PRACTICE PROBLEM
```
Imagine a router follows M/M/1. (Poisson arrival, exponential service time, 1 processor)
Arrival rate: 8 pps (λ)
Avg service rate: 12 pps (u)

P(5 pkts arrive in 1 sec)?
	- P(X=5) = (8^5)*(e^-8)/(5!) = (32768*e^-8)/120 = 9%
P(at least one pkt arrives in 100ms)?
	- (0.8^{1})*(e^{-0.8})/(1!) = 36%
Expected inter-arrival time?
	- 
P(service time less than 100 ms)?
	- 1-e^(-1*0.1) = 1-e^-0.1 = ~9.5%
Expected service time?
```