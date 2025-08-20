📘 Iterators, Generators — Summary Notes

This document summarizes the key concepts, examples, and learnings from the practice session on Iterators, Generators, and the Introduction to OOP in Python.

🔄 Iteration & Iterables

Iteration → The process of accessing elements of a sequence one by one.

Iterable → Any object that can return an iterator.

Examples of Iterables:

list → list_iterator

tuple → tuple_iterator

str → str_iterator

dict → dict_keyiterator / dict_valueiterator / dict_itemiterator

set → set_iterator

range → range_iterator

👉 Not every object is iterable. For example, int is not iterable.

⚙️ Iterators

Iterator → An object that helps traverse through data without storing everything in memory at once.

Every iterator must implement:

__iter__()

__next__()

📌 Key Points

Every iterator is also iterable.

Every iterable may or may not be an iterator.

Iterators allow lazy evaluation → values generated only when needed.

🔍 Example:

L = [1,2,3,4,5]
it = iter(L)   # get iterator
next(it)       # → 1
next(it)       # → 2
...

📏 Memory Efficiency

Lists: Take up large memory if size increases (sys.getsizeof(list)).

Range / Iterators: Very small memory footprint even for huge numbers (sys.getsizeof(range(...))).

✔ Reason: Iterators don’t store all values in memory, they generate them on demand.

🛠 Custom Iterators

We can build our own iterators by defining classes with __iter__ and __next__.

Example: Squaring Numbers

SquareRange (iterable class) → produces SquareIterator (iterator class).

Iterates and returns squares from start to end.

Example: Custom Range

MyRange (iterable) → produces numbers like range() but with custom logic.

⚡ Generators

A generator is a shortcut for building iterators.

Defined using a function with yield (instead of return).

Each yield temporarily pauses execution and remembers state.

📌 Benefits:

Simpler code (less boilerplate than custom iterators).

Memory efficient (doesn’t create the whole list in advance).

Supports lazy evaluation.

Can be chained together.

🔑 Return vs Yield

return → Ends function, gives back a single value.

yield → Produces a sequence of values, one at a time, remembering state across calls.

🔢 Examples
✅ Simple Generator
def gen():
    yield 1
    yield 2
    yield 3

✅ Squares with Generator

Instead of storing all squares in a list, generate them on demand.

✅ Fibonacci Sequence Generator

Efficiently generate Fibonacci numbers without storing them all.

🏭 Industry Use Case

Iterators and Generators are widely used in:

Reading large files (line by line).

Streaming big data.

Image processing (loading one batch at a time).

Pipelines (lazy evaluation for performance).

🔗 Generator Chaining

We can combine generators together:

Example:

Generate Fibonacci numbers → pass into another generator → square them → sum results.

sum(sq(fib(10)))  # → 1870

🚀 Key Takeaways

Iterable → Can be looped over (list, tuple, str, etc.).

Iterator → Provides sequential access using iter() and next().

Generator → Simplifies iterators using yield.

Advantages: Memory efficiency, lazy evaluation, and simpler implementation.
