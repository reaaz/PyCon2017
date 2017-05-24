# Lazy Evaulation by Joe Jevnik
 * Must be pure functions
 * Thunks (aka closuers)
## Python Tooling
 * Lambdas
 * `a = lambda: f(1, 2)` (a is a thunk produced by a lambda)
 * `b = lambda: f(a(), 4)` (same)
 * Generators
## Expressions as Trees
 * If you have multiple subexpressions with the same call, the tree model falls down since it evaluates the same call twice, this can be solved with a graph
 * Naive Thunks
 * `lambda: f(a, b)` (slow because we don't take advantage of function purity)
 * Advanced Thunks
 * Speed that up w/ memoization -- remember the result of a computation, expressions are computed at most once, requires pure functions)
 * Cell Thunks
   * Store the result default to `self.not_evaluated`
   * Override `__call__` and delete the code, args, and kwargs after the result is set, which is important for ensuring this isn't evalluated again
 * Self Updating Thunk
   * Define indirection_Code which takes the value and returns it unchanged
 * Properties
   * Naive - simple, no state [don't want to use this in practice]
   * Cell Model - moderately complex, simple state
   * Self Updating most complex, complex state
 * More Memoization
   * Memoize the construction of the deferred object instead of just the function
 * Real Example
   * Fibonacci
   * dask.delayed - defers execution to build up a graph to execute in parallel
   * Blaze - defers execution to execute expressions against different backends (numpy, SQL, Mongo)
