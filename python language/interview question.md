## hat are python iterators? 
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
 
