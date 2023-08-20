## What are the generators in python? 

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

##  yield 
##  What are python iterators?
