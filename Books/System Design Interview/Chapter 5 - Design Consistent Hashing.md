
Chapter 5: Design Consistent Hashing

Imagine you are trying to achieve horizontal scaling. You can accomplish this by spreading out data coming in to their own partitions. This spreads the load ideally evenly throughout all your servers
Now imagine you did this with a simple hashing function to figure out which server the data should go to using modulo operation:
key = hash % num_of_servers
That's all fine and dandy but what happens when a server is removed or added?
The key will now be a different value and will index another server
This can cause issues like clients connecting to the wrong server which leads to a storm of cache misses
We resolve this by incorporating Consistent Hashing 
Imagine an array of memory that can be visualized like a ring (both ends connect). The components on this ring are the servers and the keys
Keys will correspond to another server by moving clockwise along the ring until you reach a server
Adding/ removing a server will just require searching again along the ring until the next server

What issues can arrive with this approach?
There might be an uneven distribution of data because 1 server could potentially be the server closest to a big group of keys
This is solved through virtual nodes 
Which involves splitting servers into their own partitions and distributing them throughout the ring. Like server_1 becomes server_1_1, server_1_2 and etc.

Consistent hashing is pretty interesting concept, and is used by many robust systems like Amazon dynamoDB and Apache Cassandra