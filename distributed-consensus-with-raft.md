# DISTRIBUTED CONSENSUS WITH RAFT

@jxxf

- Why consensus is hard
- Distributed consensus
- Many ways, many implementations
- 2 *general buckets*:
	- Symmetric (everyone agrees)
	- Asymmetric (designated leader)
- Locality bubble
- Two generals problem A, B
	- both want attack a city
	- city can repel 1 but not both attacks
	- generals should co-ordinate their attacks to ensure destruction of city
	- city has spies to intercept communication 
	- city can only transform, not block messages
	- impossible to coordinate, cannot confirm receipt of message
- Distributed systems are hard, yo
	- Blockchains are one implementation, mostly really hard Math problems
	- Paxos, but hard to implement, maintain
		- Goal of Raft: available, replicated state machine
		- Raft is asymmetric 
			- Leader, Candidate, Follower
			- Everyone starts as a Follower
			- After a timeout, becomes a Candidate
			- If enough votes, Candidate becomes Leader
			- If not enough votes, timeout again, start over
			- Election valid outcomes: 3
- Raft: Used by Kubernetes, Docker Swarm, and more
- …

___
## Metadata
```

Tue Jun 28 14:22:28 PDT 2016
```

