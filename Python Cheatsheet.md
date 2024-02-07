## Math Operations
- `divmod()`: Takes two numbers -  `numerator, denominator` - as arguments and returns their quotient and remainder in a tuple.
	- E.g. `divmod(8, 3) =  (2, 2)`

## Custom comparator between classes

See [Merge K Sorted List solution](https://leetcode.com/problems/merge-k-sorted-lists/submissions/561547013/) on a default comparison between ListNodes:
```python
ListNode.__lt__ = lambda self, y: self.val <= y.val
```

# External Libraries

`SortedDict` from [sortedcontainers](https://grantjenks.com/docs/sortedcontainers/)
- Most methods remain the same, e.g. `.keys()`, `.items()`, `.values()`,  `.pop()`
- You can search through its sorted **keys** via: `.bisect_left(value)`, `.bisect_right(value)
- You can count the number of key-value pairs with `.count()`
- To look up items: use `.peekitem(index = -1)`