## Data Structures and Algorithms

### Unpacking iterable to variables

- Dismatch in number of elements returns error
- Discard certain values

    ~~~
    data = ['AME', 50, 91.1, (2012, 12, 21)]
    _, shares, price, _ = data
    ~~~

- Arbitrary length `*`

    ~~~
    def sum(items):
        head, *tail = items
        return head + sum(tail) if tail else head
    ~~~

### Deque

- `from collections import deque` or `collection.deque`
- `deque(iterable, maxlen)`
    - If length full, new items are added, old items are discarded from the opposite end
- Similar to list
- Can append and pop at both ends
- Method
    - `append()`, `appendleft()`
    - `pop()`, `popleft()`
    - `extend(iterable)`, `extendleft(iterable)`
    - `index(element, begin, end)`
    - `insert(index, argument)`
    - `remove()`: remove first occurrence of the value
    - `count()`
    - `reverse()`
    - `rotate(num)`
        - If num is positive, rotation occurs to right
        - If num is negative, rotation occurs to left
- `deque(maxlen = 5)`

### Find largest or smallest N items

- `nlargest(n, item)` & `nsmallest(n, item)` from `heapq`

### Sort by a given priority

- 