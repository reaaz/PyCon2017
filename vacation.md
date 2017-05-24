# Solid Snakes by Hyneck Schlawack
## Simple Software
 * Good design = ravioli, many objects/functions that are self-contained and not very aware of each other
## Complex Software
 * God objects - know too much, too many dependencies, large number of mocks/doubles to instantiate in tests
 * Subclassing - made for specialization, not code-sharing, number of rules to follow, namespace confusion, scattered logic
 * Metaclasses
# attrs (writes class boilerplate for you)
 * Gives you a simple class, validators, converters, default value
## Operational complexity
 * Distributed systems are hard, each separate system is a SPOF and each link is a SPOF as well
 * Microservices
  * Message buses
  * Tracing
  * Aggregate logging
  * Service discovery
 * Need to define clear boundaries, enables separate teams working on separate parts
 * Complexity is reality - a price you pay for getting stuff done
## Plan for stupidity
 * "I don't believe in human error" - Etsy CTO, it's a symptom of poor system design
 * Sharp edges in your product that allow people to get hurt are your fault
## Illegal State - make illegal state unrepresentable
 1. Valid after init (lots of if statements in classes are a code smell)
 2. Prevent them from being mutated to illegal
## Data Validation at Edges
 * Deeper invalid data gets, the more damage it does, sooner you catch it the more you can do
 * Do it at command line, `init()`
## Data Normalization
 * Business logic shouldn't know what JSON is
 * If you know what's in the keys of your `dict`, make it a class, `dict` only useful if you need to iterate over the keys
## Failure is inevitable
## Expect
 * Check for outages, instrument, need solid reporting
 * Prometheus - instrumentation
 * Sentry - error reporting
## Timeouts
 * One of the most important things in distributed systems
 * Circuit breaker pattern - turn off calls to failing system after certain threshold, start serving errors to client immediately (reduce strain on remote api), probe checks to see if resolved then can turn connections back on
## Redundancy
 * Have 2 of everything, and more than that of the really important thing
 * If you don't test your backups, you don't have backups
 * If you don't have multiple copies of your backups, you don't have backups
## Docs
 * Written procedures for emergencies
 * Company communication
## Deal with it
 * Don't make it any worse
 * Retries (can be super dangerous if you use the loosely [blacklisting, ddossing])
 * Back off (how long - start with a short period and back off exponentially with jitter (random number to space out retries so that we don't get flooded when all works again))
  * Can cause cascading issues if you retry at all layers, retry only at the top
  * Do not have a queue that is not limited in size, mathematically proven that they will fail
 * Don't swallow errors - make sure errors aren't silent
  * `raise AppException() from e` to chain your custom exceptions to actual exception
 * Don't try too hard
  * `sys.exit(1)` - crash only software
 * Fail fast and faily loudly - a crash or a quick 500 is better than a hang
 * Focus on recovery
  * MTTR - mean time to recovery
  * No human should be allowed in recovery, if the power goes out at the DC everything should come up on its own
 * Zero expectations
 * Fault tolerancy -> recovery
