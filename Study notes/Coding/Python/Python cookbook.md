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

## Kepp last N items

- `collections.deque`
    - `from collections import deque`
    - Similar to list
    - Can append and pop at both ends
    - Method
        - `append()`, `appendleft()`
        - `extend(iterable)`, `extendleft(iterable)`
        - `index(element, begin, end)`
        - `insert(index, argument)`
        - `remove()`: remove first occurrence of the value
        - `count()`
        - `reverse()`
        - `rotate(num)`
            - If num is positive, rotation occurs to right
            - If num is negative, rotation occurs to left