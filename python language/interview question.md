## what are python iterators? 
- Python iterators are objects that allow you to access elements of a collection one at a time
- **__iter__()** : This method returns the iterator object itself. It is required for an object to be considered an iterator.
- **__next__()** : This method returns the next value from the iterator. When there are no more items to return, it should raise the StopIteration exception to signal the end of iteration.
```python
class MyRange:
    def __init__(self, start, end):
        self.value = start
        self.end = end

    def __iter__(self):
        return self

    def __next__(self):
        if self.value >= self.end:
            raise StopIteration
        current = self.value
        self.value += 1
        return current

# Usage:
for i in MyRange(0, 5):
    print(i)
```

##  What are python generator?
- Generators in Python are a simple and powerful tool for creating iterators. Generators use the **yield** keyword to suspend execution temporarily and yield a value one at a time. This makes generators memory efficient as they don’t generate the entire sequence of values upfront but rather generate values on-demand.
- use **next** to call generator
  
## yield
- Function Behavior: When a function contains a yield keyword, it no longer behaves like a regular function. Instead of returning a single value (like with the return statement), it returns a generator object.

- Execution State: One of the most powerful aspects of yield is that it allows the function to "pause" its execution. When the generator's next() method is called, execution starts or resumes until the next yield is encountered, then it pauses again, saving all its state (like local variables).

- Multiple Yields: A function can have multiple yield statements. Every time next() is called on the generator, execution resumes from where it was paused and continues until the next yield is encountered.

- **Return**: Ends the function's execution and returns a value to the caller.
- **Yield**: Produces a value for iteration but "pauses" the function's execution, allowing the function to later resume from where it left off.

##  How does break, continue, and pass work?
- break, continue, and pass are control flow statements in Python
- break:
    - Purpose: Exits the current loop prematurely, bypassing the remainder of its body.
    - Common Use: To exit a loop when a certain condition is met.
    - ```python
      for i in range(10):
        if i == 5:
            break
        print(i)
        # Output: 0 1 2 3 4
      ```
- continue:
    - Purpose: Skips the rest of the current iteration and jumps to the next iteration of the loop.
    - Common Use: To avoid executing certain parts of the loop body for specific iterations.
    - ```python
      for i in range(5):
        if i == 2:
            continue
      print(i)
      #Output: 0 1 3 4
      ```


