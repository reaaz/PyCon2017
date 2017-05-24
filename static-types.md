# Static Types for Python
## Motivation
## Considering our options
 1. Add special docstrings or comments
  * Works ok but people forget to update them
  * Become untrustworthy and therefore useless
 2. Infer types throughout the whole program
  * Unsolved problem
  * Doesn't help understanding unless types ready at hand
  * Hardest most dynamic code obstructs types everywhere
 3. Add static types to Python
  * Must be able to introduced gradually
  * Still a lot of work to implement
## Demo
 * `mypy` package
 * `--strict-optional` flag
 * Can use `Optional` for functions that return a type or None
## How Mypy works
### Symbol Tables
 * Internal mypy data structure
 * One for each module, class, function
 * Map from name to type
 * Built by analysing source code
 * Nested
## Annotating an Existing Codebase
 * Annotate your code from the bottom up instead of from the main entrypoint of your app
 * Can add files as arguments to `mypy` to check multiple files, go from the leaves up
 * Ignoring modules
  * `--follow-imports=skip --ignore-missing-imports` flags
 * Keep your code mypy clean - run it with your test in your CI system
## Mypy at Dropbox
 * PyCharm code completion ties into type annotations
