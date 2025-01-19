5/15/24

**Data dependency drives your performance**
Data dependency cases:
1. No data dependency - most ideal but rarely happens, just add more computers/shards/partitions to scale
    Webhook system
    Redpanda has something (transforms) that attempts to solve no data dependency
2. Deferred Inter-Event Data Dependency (DEDD) - most like real-world
    Defer data dependency. This allows you to write with more speed.
    Data dependency will be resolved later down the line
    most practical
3. Streaming Inter-Event Data Dependency (SEDD)
    Resolving data dependency at stream time.
    Uses: real time
    A big investment to be successful at this
    
Trade off between data dependency and max throughput
Data dependency introduces data latency.


**How to build a more robust event-driven architecture:**
Typical system: microserivces talking to microservices, databases, producer/consumers
Normally categorize different message queues for each subject/grouping

Schema Registry
- Introducing contracts to help build robust system: similar to rest api contracts.
- Define a schema: data payload details, data file encoding (avro, protobuf, json)
- Producer downloads from Schema Registry a schema format to serialize payload, and attach schema id -> send to Consumer, Consumer uses schema ID to retrieve schema from Schema Registry which allows it to deserialize the payload
- If you're critical about performance, protobuf might be the solution.
- Should producer submit schema to schema registry? Or developer. If producer does it, this ensures most updated version of the schema. If developer, this is an extra guardrail.
- Backward and Forward compatibility for schemas (different versions of a schema). How to achieve? Use default values for the fields
- Expose Schema Registry as REST API, inside the schema registry, you'll have a Topic to stream the schemas
- If you're not going to change your schema in the future, probably don't need schema registry. 

Event validation:
- If something goes wrong with schema/payload on Consumer, send it to another sevice which will look into it and perform correction/remedy. OR have a Validator and send successful payloads to Consumer while sending bad ones to correction/remedy service.
- These services introduce more network calls though.
- There is a way to have In-broker validation: redpanda data transforms perform this. This is stateless, quick, simple but requires external data dependencies, complex processing (flink and others can better handle this)
- Server side validations: 

Tuning for trade offs
- Pretty much tune Producer, Broker, Consumer to best fit your system. 
    - For tuning the Broker: tune infrastructure (horizontal scaling for computers, location region to reduce latency), OS (disk i/o, read and write bandwidth), Broker (# of brokers, replicas, partitions, log segment size). Brokers have a partitioning algorithm for Producer -> queue -> Consumer (Round robin, Hahsing Key partition, custom one). Idempotency, kafka/redpanda only guarantees ordering in partition only. There is more overhead with larger partitions (larger metadata that changes, follower heartbeats). Additionally, when consumer goes down, you have to rebalance your partitioning.
     - For tuning the Producer: In the case of failures, Can have Ack=1: redpanda writes to disk before ack to Producer (kafka writes to page cache?), optional writing to cache for redpanda. Ack=0: dones't wait for acks and doesn't retry sending messages. Ack=all: majority of replicas acknowledge. So, this is tradeoff between fault tolerance and throughput
    - For tuning Consumer: message size slows throughput, fetch frequency
    - In summary: For the Broker, more partitions = more parallel processing but more cost. For producers, if you don't care about reliable delivery then you can have less acks. For consumer, think about fetch times and message sizes
- Messaging queues has limited disk space. Retention limits. Redpanda stores dropped events in storage (S3) and then rehydrate the topic with them. This is slow though

- Summary for robust systems: How to deal with correct payload schemas between producers/consumers with schema registry, approaches to event validations to resolve incorrect payloads, and tuning parameters for producer, broker, consumer for best fit for tradeoffs


**How do we integrate Distributed Data stores across event-driven systems**
Domain driven design -> complexity of business logic
Event driven -> complexity of data infrastructure, volumn of data

Why do we need ScyllaDB?
- Need high performance, low latency databases. Wasn't widespread in the past. Now, modern databases like ScyallaDB
- Stateless vs stateful prcoessing
	- Keep doing stateless
	- Re-think stateful processing
Example: Social media application
- Follows, followers
- Database relationships:
- Improvements:
	- Consistency guarantees: Apply common patterns:
		- Outbox - for non-idempotent operations
		- Listen to Yourself
	- Publish database events (CDC)
		- Strongly consistent push notifications
		- Feed other downstream app/services
	- WebSockets for real-time communication / async callbacks