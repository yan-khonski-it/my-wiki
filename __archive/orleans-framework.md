# Orleans


- [Introduction to the Actor Model for Concurrent Computation: Tech Talks @ AppNexus](https://youtu.be/lPTqcecwkJg)

- [Orleans at Microsoft](https://youtu.be/KhgYlvGLv9c)
> Distributed transactions: banking. To withdraw from one account and deposit to another account as a transaction, even if the accounts are stored in different databases.
Orleans will work as a distributed transaction manager (? really).

> grains exist at most once (by id) even in multiple clusters (Dynamic Fraud Protection, for example).
> Exactly once processing - no at most once. No automatic retry of message, by defaul.
Effectively once processing.

Orleans grain can be invoked as singleton, so only one thread can execute it at a time.

- https://www.youtube.com/live/R0ODfwU6MzQ?feature=share

Actors
https://youtu.be/lPTqcecwkJg
Process exactly one message at a time; no additional concurrency.

> Do not communicate by sharing memory; instead, share memory by communicating.


Akka at Microsoft
[When and How to Use the Actor Model An Introduction to Akka NET Actors](https://youtu.be/0KnIMDoJpZs)

and virtual actors
TODO MSFT documetation

[How to build real-world applications with Orleans - John Azariah and Sergey Bykov](https://youtu.be/7OVU9Mqqzgs)
