# Rate Limiter LLD Design

## Problem Statement

Design a rate limiter system that restricts the number of requests a user or service can make within a specified time window. This is commonly used to prevent abuse and ensure fair usage of resources in distributed systems and APIs.

## Key Concepts

- **Token Bucket / Leaky Bucket Algorithms**
- **Fixed Window / Sliding Window Counters**
- **Concurrency Handling**
- **Distributed Rate Limiting**
- **Throttling vs. Rejecting Requests**

## Example

Suppose an API allows a maximum of 100 requests per user per minute. If a user exceeds this limit, further requests are rejected until the next time window.

## When to Use

- Protect APIs from abuse or denial-of-service attacks
- Enforce fair usage policies
- Prevent resource exhaustion in distributed systems

## How to Use

- Integrate the rate limiter as middleware in your API/service
- Choose an algorithm based on accuracy and performance needs
- Store counters in memory or distributed cache (e.g., Redis) for scalability

## Advantages

- Prevents abuse and overload
- Ensures fair resource allocation
- Can be tuned for different use cases

## Disadvantages

- May add latency if implemented inefficiently
- Distributed rate limiting requires careful synchronization
- May block legitimate burst traffic if not tuned properly

---

# Hands-On Example: Token Bucket Algorithm (Python)

```python
import time
class TokenBucket:
    def __init__(self, rate, capacity):
        self.rate = rate  # tokens per second
        self.capacity = capacity
        self.tokens = capacity
        self.last_refill = time.time()

    def allow_request(self):
        now = time.time()
        elapsed = now - self.last_refill
        self.tokens = min(self.capacity, self.tokens + elapsed * self.rate)
        self.last_refill = now
        if self.tokens >= 1:
            self.tokens -= 1
            return True
        return False

bucket = TokenBucket(rate=2, capacity=5)
for i in range(10):
    if bucket.allow_request():
        print(f"Request {i+1}: Allowed")
    else:
        print(f"Request {i+1}: Denied")
    time.sleep(0.3)
```

---

You can adapt this logic for distributed systems using Redis or other shared storage for counters.
