# Async in Python 3.6 and Beyond by Yuriy Selivanov
## Why async/await?
 * Readability
  * Better than callbacks or Promises
  * Easier to reason about than threads or gevent code
  * Promotes better patterns like message passing
 * Efficiency
  * No threads: no gil problem
  * Less memory per connection
  * Can handle thousands of long lasting connections
* What is async/await (syntax new in python 3.5, 3.6 adds async generators for list comprehensions, yield from may come in 3.7)
 * Protocol
  * Based on iterator protocol
 * Frameworks
  * Twisted and Tornado - can use async/await today
   * Twisted is the mother of async in Python
   * both own big ecosystems and mindshare
   * can/will run on top of asyncio (already in tornado, coming to twisted)
  * Curio and Trio
   * explore new approaches
   * make async easier/safer to use
   * not mainstream
## Let's talk about async.io
### Foundation
* Low-level APIs - callbacks, transports, protocols, network, subprocesses, signals
* async/await - run coroutines, streams, sockets, subprocesses, locks
* Mainstream - stable and forever supported, healthy ecosystem, HTTP: `aiohttp` and `Sanic`, DBs: `asyncpg`, etc
* Pluggable event loop
 * `uvloop` - make asyncio 2-4 times faster, stable, production-safe
 * PyO_3 (write Rust in Python -> Tokio), incomplete and experimental, aims for safety and performance
## What's next for asyncio?
* Goals for 3.7
 * Run/use Twisted on/in asyncio
 * Maybe curio and trio can be re-built on top of asyncio
 * Rust loop
 * Usability
  * Documentation overhaul in 3.7 - currently too low level
  * asyncio is designed to pass event loop explicitly
  * in Python 3.6 `asyncio.get_event_loop()` works predictably in async functions so you don't need to pass the event loop explicitly
 * `start_tls()`
 * Call/task context APIs - difficult, may be needed for Flask rewrite
 * async REPL
## Need your help
 * `python-tulip` mailing list
 * Ask for new features
 * All of CPython is on Github
