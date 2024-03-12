Chapter 4: Design Rate Limiter

We are asked to design a rate limiter. Rate limiters are used to control traffic by limiting the number of requests coming in. This is helpful for a couple reasons.

Prevent DDoS attacks
Reduce costs
Prevent overloading servers
Allow reallocation of resources for prioritizing more important APIs
 
There are multiple algorithms for rate limiting:
token bucket
leaking bucket
fixed window counter
sliding window log
sliding window counter
token bucket is the easiest to implement. Imagine a bucket that periodically generates tokens until it is full (any overflow is discarded)

When a request comes in, it uses the amount of tokens needed if available from the bucket

Some considerations for rate limiting:
What are my rules? When do I start limiting requests
Need observability into the limiter. Are my rate limiting algorithms performing well, are my rules sufficient. Metrics are highly useful to graph performance
