
Unique IDs are important for distributed systems because you need a way to reference a server. There should only be 1 server to 1 unique id. How are these ids generated such that every server has a unique one?

## Step 1 - Understand the problem, establish design scope

What are the characteristics of unique ids?
must be unique and sortable
contain numerial values
64 bits
ability to generate thousands of ids per second


## Step 2 - Propose high level design:
Multiple options to generate unique IDs:
Multi-master replication
Universally Unique Identifier (UUID)
Ticket Server
Twitter snowflake approach

Multi-master replication : 
Just use database's auto_increment feature which assigns and increments an id for each row. The problem is that it's hard to scale with multiple databases and servers. Also doesn't scale well when server is added/removed

UUID: 
128-bit number used to identify information. Low probability of collisions. Each web server contains ID generator, they generate IDs independently. No coordination required between servers. ID generator scales with the web server which is easier. The cons is that IDs don't go up with time and 128 bits is pretty long. These IDs could also be non-numeric

Ticket Server:
All web servers coordinate with a central ticketing server. Idea is to use a centralized auto_increment like for the databases but with just 1 server and give out IDs to web servers asking for one. This is easy to implement for small/mid sized applications but it's a single point of failure for large systems. Need to introduce synchronization which is a challenge of its own

Twitter Snowflake Approach:
Twitter's unique ID generator called snowflake. It divides a 64-bit ID into different sections. Each section represents something in bits, ie. timestamp, datacenter id, machine id, sequence number. Any change to datacenter or machine ids need to be carefully done to prevent collisions

## Step 3 - Design Deep Dive:
For example. if picking twitter snowflake approach, go into detail how the bits are setup. 

## Step 4 - Wrap Up:
Talk about any future enhancements.
Things to think about: clock synchronization, network time protocol. What if timing is off? 