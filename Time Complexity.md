
## Logarithmic Time Complexity

### Logarithmic + Factorial
See [this example in Search a 2D Matrix II](https://leetcode.com/problems/search-a-2d-matrix-ii/submissions/1160796566/) (also see [editorial](https://leetcode.com/problems/search-a-2d-matrix-ii/editorial/): Approach 2, Binary Search) - we can distill a logarithmic time complexity to a factorial one:

```
O(log(n)+log(n−1)+log(n−2)+…+log(1))
= O(log(n⋅(n−1)⋅(n−2)⋅…⋅1))
= O(log(1⋅…⋅(n−2)⋅(n−1)⋅n))
= O(log(n!))
```

The above is an [[asymptotic runtime]]. We can also conclude that:
```
log(n!) = O(nlogn)
```