# Memory types
 - Memory is separated by speed (fast -> small but expensive, large -> vice versa)
	 - Registers
	 - L1 Cache
	 - L2 Cache
	 - L3 Cache
	 - RAM
	 - SSD
	 - HDD
 - Cache locality
	 - Temporal:
		 - Recently accessed memory is likely to be reaccessed (loops & more)
	 - Spatial:
		 - If you access memory, you're likely to access nearby memory
 - Cache lines
	 - When memory is accessed, an entire line is (64 bytes on most x86)
	 - Cache miss:
		 - When you don't advantage temporal/spacial locality, access takes longer
		 - Occurs on the first access, always (cache starts as empty)

# Variable storage (Memory Alignment)
- Memory locations are based on data size (multiples of data size)
- Integers (Java -> 4 Bytes)
	- 0x1000, 0x1004, 0x1008, etc
- Longs (Java -> 8 Bytes)
	- 0x1000, 0x1008, 0x1010, etc. (Remember, addresses are hex)
- Misaligned data cause issues
	- CPUs read memory in chunks ()
	- Misaligned data can require two reads
	- Can cause craching