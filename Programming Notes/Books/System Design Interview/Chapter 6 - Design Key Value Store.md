
CAP Theorem 

3 guarantees:
Consistency
Availability
Partition Tolerance

This theorem states that you can only pick 2 out of the 3 guarantees. 1 has to be sacrificed to support the other 2

Typically, you decide on 2 options
CP (consistency and partitioning)
AP (availiability and partitioning)

Partitioning is always needed in order to deal with network failures, so CA (consistency and availability) will never work in real life systems
Consistency means all servers must present the same data to a user at any time
Availability means that users see any data even if it's not updated yet

Servers are distributed on a ring using consistent hashing
A server is selected to be a coordinator which the client communicates with (send request, get response)

How to do Failure Detection?
Gossip Protocol: servers periodically increments heartbeat counter. Each server periodically propagates heartbeats to the other servers. If heartbeat has not increased for more than a predefined setting, the server is considered offline

Another server can process that offline server temporarily

If a server is offline permanently, you handle this by implementing anti entropy protocol to keep replicas in sync. This is done via Merkle Tree for inconsistency detection. Every non-leaf node in the tree is labeled with the hash of its children nodes
