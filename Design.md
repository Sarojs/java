1. What is CAP Theorem?
Ans:
Another way that we might think about availability is in relation to the CAP theorem. The theorem states that a distributed system, one made up of multiple nodes storing data, cannot simultaneously provide more than two out of the following three guarantees:

Consistency: Every read request receives the most recent write or an error when consistency can’t be guaranteed.
Availability: Every request receives a non-error response, even when nodes are down or unavailable.
Partition tolerance: The system continues to operate despite the loss of an arbitrary number of messages between nodes.
ref: https://docs.aws.amazon.com/whitepapers/latest/availability-and-beyond-improving-resilience/cap-theorem.html

